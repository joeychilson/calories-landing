<script lang="ts">
	import { resolve } from '$app/paths';
	import { LogoIcon } from '$lib/components/icons';

	const homeHref = resolve('/');
	const featuresHref = `${homeHref}#features`;
	const pricingHref = `${homeHref}#pricing`;
	const privacyHref = resolve('/privacy');
	const termsHref = resolve('/terms');
</script>

<footer class="py-8">
	<div class="mx-auto max-w-4xl px-4">
		<div class="flex flex-col md:flex-row items-center justify-between gap-4">
			<a href={homeHref} class="flex items-center gap-1">
				<LogoIcon class="size-5 text-primary" />
				<span class="text-lg font-semibold">Calories</span>
			</a>
			<nav class="flex items-center gap-6 text-sm text-muted-foreground">
				<a href={featuresHref} class="hover:text-foreground transition-colors">Features</a>
				<a href={pricingHref} class="hover:text-foreground transition-colors">Pricing</a>
				<a href={privacyHref} class="hover:text-foreground transition-colors">Privacy</a>
				<a href={termsHref} class="hover:text-foreground transition-colors">Terms</a>
			</nav>
			<p class="text-sm text-muted-foreground">
				&copy; {new Date().getFullYear()} float32
			</p>
		</div>
	</div>
</footer>
