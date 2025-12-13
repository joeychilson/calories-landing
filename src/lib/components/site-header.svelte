<script lang="ts">
	import { resolve } from '$app/paths';
	import { PUBLIC_APP_URL } from '$env/static/public';
	import {
		ChefHatIcon,
		LoginIcon,
		LogoIcon,
		MoonIcon,
		SunIcon,
		WalletIcon
	} from '$lib/components/icons';
	import { Button } from '$lib/components/ui/button';
	import { toggleMode } from 'mode-watcher';

	const homeHref = resolve('/');
	const featuresHref = `${homeHref}#features`;
	const pricingHref = `${homeHref}#pricing`;
	const signinHref = `${PUBLIC_APP_URL}/signin`;
</script>

<header class="sticky top-0 z-50 bg-background">
	<div class="mx-auto flex h-14 max-w-4xl items-center px-4">
		<div class="flex flex-1 items-center gap-1">
			<a href={homeHref} class="flex items-center gap-1">
				<LogoIcon class="size-5 text-primary" />
				<span class="text-lg font-semibold">Calories</span>
			</a>
			<button
				onclick={toggleMode}
				class="flex items-center justify-center size-9 rounded-md text-muted-foreground hover:text-foreground"
			>
				<SunIcon class="size-4 rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
				<MoonIcon
					class="absolute size-4 rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
				/>
				<span class="sr-only">Toggle theme</span>
			</button>
		</div>
		<nav class="hidden md:flex items-center gap-1">
			<Button
				variant="ghost"
				href={featuresHref}
				class="flex items-center gap-2 px-3 py-2 text-muted-foreground"
			>
				<ChefHatIcon class="size-4" />
				<span class="text-sm">Features</span>
			</Button>
			<Button
				variant="ghost"
				href={pricingHref}
				class="flex items-center gap-2 px-3 py-2 text-muted-foreground"
			>
				<WalletIcon class="size-4" />
				<span class="text-sm">Pricing</span>
			</Button>
		</nav>
		<div class="flex flex-1 justify-end">
			<Button size="sm" href={signinHref} class="flex items-center gap-2">
				<LoginIcon class="size-4" />
				<span>Sign In</span>
			</Button>
		</div>
	</div>
</header>
