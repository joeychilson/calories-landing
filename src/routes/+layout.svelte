<script lang="ts">
	import { page } from '$app/state';
	import favicon from '$lib/assets/favicon.svg';
	import SiteFooter from '$lib/components/site-footer.svelte';
	import SiteHeader from '$lib/components/site-header.svelte';
	import { ModeWatcher } from 'mode-watcher';
	import '../app.css';

	const isError = $derived(page.status >= 400);
	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
	<link
		href="https://fonts.googleapis.com/css2?family=Geist+Mono:wght@400;500;600;700&display=swap"
		rel="stylesheet"
	/>
	<meta property="og:type" content="website" />
	<meta property="og:site_name" content="Calories" />
	<meta name="twitter:card" content="summary_large_image" />
</svelte:head>

<ModeWatcher />
<div class="flex min-h-screen flex-col">
	{#if !isError}
		<SiteHeader />
	{/if}
	<div class="flex flex-1 flex-col">
		{@render children()}
	</div>
	{#if !isError}
		<SiteFooter />
	{/if}
</div>
