<script lang="ts">
	import { resolve } from '$app/paths';
	import { page } from '$app/state';
	import {
		AlertIcon,
		ChevronLeftIcon,
		HomeIcon,
		PageNotFoundIcon,
		SecurityIcon,
		ServerIcon,
		WifiErrorIcon
	} from '$lib/components/icons';
	import SiteFooter from '$lib/components/site-footer.svelte';
	import SiteHeader from '$lib/components/site-header.svelte';
	import { Button } from '$lib/components/ui/button';
	import type { Component } from 'svelte';

	type ErrorInfo = {
		icon: Component<{ class?: string }>;
		iconClass: string;
		bgClass: string;
		title: string;
		message: string;
	};

	const errors: Record<number, ErrorInfo> = {
		404: {
			icon: PageNotFoundIcon,
			iconClass: 'text-muted-foreground',
			bgClass: 'bg-muted',
			title: 'Page not found',
			message: "Sorry, we couldn't find the page you're looking for."
		},
		403: {
			icon: SecurityIcon,
			iconClass: 'text-destructive',
			bgClass: 'bg-destructive/10',
			title: 'Access denied',
			message: "You don't have permission to view this page."
		},
		500: {
			icon: ServerIcon,
			iconClass: 'text-destructive',
			bgClass: 'bg-destructive/10',
			title: 'Server error',
			message: 'Something went wrong on our end. Please try again later.'
		},
		503: {
			icon: WifiErrorIcon,
			iconClass: 'text-muted-foreground',
			bgClass: 'bg-muted',
			title: 'Service unavailable',
			message: "We're temporarily offline for maintenance. Please check back soon."
		}
	};

	const defaultError: ErrorInfo = {
		icon: AlertIcon,
		iconClass: 'text-destructive',
		bgClass: 'bg-destructive/10',
		title: 'Something went wrong',
		message: 'An unexpected error occurred.'
	};

	const errorInfo = $derived(errors[page.status] ?? defaultError);
	const displayMessage = $derived(page.error?.message || errorInfo.message);
</script>

<svelte:head>
	<title>{errorInfo.title} | Calories</title>
	<meta name="robots" content="noindex" />
</svelte:head>

<SiteHeader />

<main class="flex flex-1 flex-col items-center justify-center p-4 text-center">
	<div class="flex size-16 items-center justify-center rounded-full {errorInfo.bgClass} mb-4">
		<errorInfo.icon class="size-7 {errorInfo.iconClass}" />
	</div>

	<h1 class="mb-2 text-xl font-semibold">{errorInfo.title}</h1>
	<p class="mb-6 max-w-xs text-sm text-muted-foreground">{displayMessage}</p>

	<div class="flex gap-2">
		<Button variant="outline" size="sm" onclick={() => window.history.back()}>
			<ChevronLeftIcon class="size-4" />
			Go back
		</Button>
		<Button href={resolve('/')} size="sm">
			<HomeIcon class="size-4" />
			Home
		</Button>
	</div>

	<span class="mt-8 font-mono text-xs text-muted-foreground/50">
		{page.status}
	</span>
</main>

<SiteFooter />
