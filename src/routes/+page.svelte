<script lang="ts">
	import { PUBLIC_APP_URL } from '$env/static/public';
	import {
		CheckIcon,
		ChevronLeftIcon,
		ChevronRightIcon,
		EllipsisIcon,
		LogoIcon,
		ScanImageIcon,
		TargetIcon,
		TrendingDownIcon,
		TrendingUpIcon,
		UserIcon,
		WeightScaleIcon
	} from '$lib/components/icons';
	import { Button } from '$lib/components/ui/button';

	const features = [
		'Log meals by photo or description',
		'Dietitian-level accuracy',
		'Track calories and macros',
		'Set personalized goals',
		'Monitor weight over time',
		'Simple, clean interface',
		'Photos analyzed, never stored',
		'7-day free trial'
	];
</script>

<svelte:head>
	<title>Calories - Simple nutrition tracking</title>
	<meta
		name="description"
		content="A simple app to track your meals, calories, and macros. Log food by photo or description. No complexity, just results."
	/>
	<meta property="og:type" content="website" />
	<meta property="og:title" content="Calories - Simple nutrition tracking" />
	<meta
		property="og:description"
		content="A simple app to track your meals, calories, and macros. Log food by photo or description. No complexity, just results."
	/>
	<meta property="og:url" content="https://burncalories.app" />
	<meta property="og:site_name" content="Calories" />
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:title" content="Calories - Simple nutrition tracking" />
	<meta
		name="twitter:description"
		content="A simple app to track your meals, calories, and macros. Log food by photo or description. No complexity, just results."
	/>
</svelte:head>

<main class="flex-1">
	<section class="relative pt-8 pb-40 md:pt-12 md:pb-52 overflow-hidden">
		<div class="container px-4 md:px-6 mx-auto">
			<div class="flex flex-col items-center text-center gap-6 max-w-3xl mx-auto mb-12">
				<h1 class="text-4xl md:text-6xl font-bold tracking-tight text-balance">
					Simple nutrition <span class="text-primary">tracking.</span>
				</h1>
				<p class="text-lg text-muted-foreground text-balance max-w-xl">
					Log meals by photo or description. Track your calories and macros without the complexity.
				</p>
				<div class="flex flex-col sm:flex-row gap-4 w-full sm:w-auto">
					<Button size="lg" class="gap-2" href="{PUBLIC_APP_URL}/signin">
						Start Free Trial <ChevronRightIcon class="size-4" />
					</Button>
				</div>
			</div>
			<div class="relative mx-auto max-w-md perspective-1000">
				<div
					class="relative rounded-xl border bg-background shadow-2xl overflow-hidden transform rotate-x-12 transition-transform duration-500 hover:rotate-0"
				>
					<div class="p-4 space-y-4 bg-background">
						<div class="flex items-center justify-between py-2">
							<div class="size-9 flex items-center justify-center">
								<ChevronLeftIcon class="size-5" />
							</div>
							<div class="flex flex-col items-center gap-0.5">
								<span class="text-xs text-muted-foreground">2025</span>
								<span class="text-lg font-semibold">Today</span>
							</div>
							<div class="size-9 flex items-center justify-center">
								<ChevronRightIcon class="size-5" />
							</div>
						</div>
						<div class="flex justify-center">
							<div class="relative flex items-center justify-center">
								<svg width="160" height="160">
									<circle
										cx="80"
										cy="80"
										r="74"
										fill="none"
										stroke="currentColor"
										stroke-width="12"
										class="text-muted"
									/>
									<path
										d="M 80 6 A 74 74 0 0 1 154 80"
										fill="none"
										stroke="var(--chart-1)"
										stroke-width="12"
										stroke-linecap="round"
									/>
								</svg>
								<div class="absolute inset-0 flex flex-col items-center justify-center">
									<span class="text-xs text-muted-foreground uppercase tracking-wider"
										>Remaining</span
									>
									<span class="text-3xl font-bold">1460</span>
									<span class="text-sm text-muted-foreground">kcal</span>
								</div>
							</div>
						</div>
						<div class="flex justify-center gap-4">
							<div class="flex min-w-24 flex-col gap-1">
								<div class="flex items-baseline gap-1">
									<span class="text-sm font-semibold">30</span>
									<span class="text-xs text-muted-foreground">/177g</span>
								</div>
								<div class="h-1.5 w-full rounded-sm bg-muted">
									<div
										class="h-full rounded-sm"
										style="width: 17%; background: oklch(0.65 0.12 250)"
									></div>
								</div>
								<span class="text-xs uppercase tracking-wider text-muted-foreground">Protein</span>
							</div>
							<div class="flex min-w-24 flex-col gap-1">
								<div class="flex items-baseline gap-1">
									<span class="text-sm font-semibold">38</span>
									<span class="text-xs text-muted-foreground">/211g</span>
								</div>
								<div class="h-1.5 w-full rounded-sm bg-muted">
									<div
										class="h-full rounded-sm"
										style="width: 18%; background: oklch(0.75 0.14 70)"
									></div>
								</div>
								<span class="text-xs uppercase tracking-wider text-muted-foreground">Carbs</span>
							</div>
							<div class="flex min-w-24 flex-col gap-1">
								<div class="flex items-baseline gap-1">
									<span class="text-sm font-semibold">28</span>
									<span class="text-xs text-muted-foreground">/57g</span>
								</div>
								<div class="h-1.5 w-full rounded-sm bg-muted">
									<div
										class="h-full rounded-sm"
										style="width: 49%; background: oklch(0.65 0.16 15)"
									></div>
								</div>
								<span class="text-xs uppercase tracking-wider text-muted-foreground">Fat</span>
							</div>
						</div>
						<div class="flex w-full items-center gap-3 p-2">
							<div class="relative flex size-12 items-center justify-center">
								<svg class="size-full -rotate-90" viewBox="0 0 40 40">
									<circle
										cx="20"
										cy="20"
										r="17"
										fill="none"
										class="stroke-muted"
										stroke-width="3"
									/>
									<circle
										cx="20"
										cy="20"
										r="17"
										fill="none"
										class="stroke-primary"
										stroke-width="3"
										stroke-linecap="round"
										stroke-dasharray="106.81"
										stroke-dashoffset="85"
									/>
								</svg>
								<WeightScaleIcon class="absolute size-4 text-muted-foreground" />
							</div>
							<div class="min-w-0 flex-1">
								<div class="flex items-baseline gap-1">
									<span class="text-lg font-bold tabular-nums">193</span>
									<span class="text-xs text-muted-foreground">/ 180 lbs</span>
								</div>
								<span class="text-xs font-medium uppercase tracking-wider text-muted-foreground"
									>13.0 lbs to go</span
								>
							</div>
							<div
								class="flex items-center gap-1 rounded-md px-2 py-1 text-xs font-bold bg-emerald-500/10 text-emerald-500"
							>
								<TrendingDownIcon class="size-3" />
								-1.0
							</div>
						</div>
						<div class="flex h-full flex-col">
							<div class="flex shrink-0 items-center justify-between">
								<div class="flex items-baseline gap-2">
									<h2 class="text-lg font-semibold">Meals</h2>
									<span
										class="rounded-full bg-muted px-2 py-0.5 text-xs font-medium text-muted-foreground"
										>1</span
									>
								</div>
								<Button variant="default" size="sm">
									<span>+</span> Log Meal
								</Button>
							</div>
							<div class="mt-2 space-y-2">
								<div
									class="group rounded-xl border-l-4 bg-muted dark:bg-muted/30"
									style="border-left-color: var(--chart-1)"
								>
									<div class="flex min-w-0 flex-1 flex-col gap-1.5 p-2.5">
										<div class="flex items-start justify-between gap-2">
											<div class="min-w-0 flex-1">
												<h3 class="line-clamp-1 font-bold leading-snug">Cheeseburger</h3>
												<p class="text-xs text-muted-foreground">2:17 AM</p>
											</div>
											<EllipsisIcon class="size-4 shrink-0 text-muted-foreground" />
										</div>
										<div class="flex items-center justify-between">
											<div class="flex items-center gap-1">
												<span
													class="rounded-sm px-1.5 py-0.5 text-xs font-semibold bg-macro-protein/15 text-macro-protein"
													>30g P</span
												>
												<span
													class="rounded-sm px-1.5 py-0.5 text-xs font-semibold bg-macro-carbs/15 text-macro-carbs"
													>38g C</span
												>
												<span
													class="rounded-sm px-1.5 py-0.5 text-xs font-semibold bg-macro-fat/15 text-macro-fat"
													>28g F</span
												>
											</div>
											<div class="flex items-baseline gap-0.5 rounded-md bg-foreground/5 px-2 py-1">
												<span class="text-base font-semibold tabular-nums leading-none">540</span>
												<span
													class="text-xs font-semibold uppercase tracking-wide text-muted-foreground"
													>kcal</span
												>
											</div>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
					<nav class="flex items-center justify-around bg-background">
						<div class="flex flex-col items-center gap-1 px-3 py-2 text-primary">
							<LogoIcon class="size-5" />
							<span class="text-xs uppercase tracking-wider">Calories</span>
						</div>
						<div class="flex flex-col items-center gap-1 px-3 py-2 text-muted-foreground">
							<TrendingUpIcon class="size-5" />
							<span class="text-xs uppercase tracking-wider">Progress</span>
						</div>
						<div class="flex flex-col items-center gap-1 px-3 py-2 text-muted-foreground">
							<UserIcon class="size-5" />
							<span class="text-xs uppercase tracking-wider">You</span>
						</div>
					</nav>
				</div>
				<div
					class="absolute -z-10 top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[120%] h-[120%] bg-primary/5 blur-3xl rounded-full pointer-events-none"
				></div>
			</div>
		</div>
	</section>

	<section class="py-12">
		<div class="container px-4 md:px-6 mx-auto">
			<div class="text-center max-w-2xl mx-auto mb-12">
				<h2 class="text-3xl font-bold tracking-tight sm:text-4xl mb-4">Tracking made simple</h2>
				<p class="text-muted-foreground text-lg">No complicated databases or tedious data entry.</p>
			</div>

			<div class="grid md:grid-cols-3 gap-8 max-w-4xl mx-auto">
				<div class="text-center">
					<div
						class="size-12 rounded-full bg-primary/10 text-primary flex items-center justify-center mx-auto mb-4 text-xl font-bold"
					>
						1
					</div>
					<h3 class="font-bold mb-2">Log your meal</h3>
					<p class="text-sm text-muted-foreground">
						Snap a photo, describe what you ate, or enter it manually.
					</p>
				</div>

				<div class="text-center">
					<div
						class="size-12 rounded-full bg-primary/10 text-primary flex items-center justify-center mx-auto mb-4 text-xl font-bold"
					>
						2
					</div>
					<h3 class="font-bold mb-2">Dietitian-level accuracy</h3>
					<p class="text-sm text-muted-foreground">
						Calories and macros are calculated automatically.
					</p>
				</div>

				<div class="text-center">
					<div
						class="size-12 rounded-full bg-primary/10 text-primary flex items-center justify-center mx-auto mb-4 text-xl font-bold"
					>
						3
					</div>
					<h3 class="font-bold mb-2">Track your progress</h3>
					<p class="text-sm text-muted-foreground">
						See your daily totals and work toward your goals.
					</p>
				</div>
			</div>
		</div>
	</section>

	<section id="features" class="py-12">
		<div class="container px-4 md:px-6 mx-auto">
			<div class="text-center max-w-2xl mx-auto mb-16">
				<h2 class="text-3xl font-bold tracking-tight sm:text-4xl mb-4">
					Everything you need, nothing you don't
				</h2>
				<p class="text-muted-foreground text-lg">Simple tools to help you eat better.</p>
			</div>

			<div class="grid md:grid-cols-3 gap-4 max-w-4xl mx-auto">
				<div class="rounded-2xl border p-6 shadow-xs dark:bg-input/30">
					<div
						class="size-11 rounded-xl flex items-center justify-center mb-4"
						style="background: oklch(0.7 0.13 50 / 0.15); color: oklch(0.7 0.13 50)"
					>
						<ScanImageIcon class="size-5" />
					</div>
					<h3 class="text-base font-bold mb-2">Easy Meal Logging</h3>
					<p class="text-sm text-muted-foreground leading-relaxed">
						Snap a photo or describe what you ate. Dietitian-level accuracy for calories and macros.
					</p>
				</div>

				<div class="rounded-2xl border p-6 shadow-xs dark:bg-input/30">
					<div
						class="size-11 rounded-xl flex items-center justify-center mb-4"
						style="background: oklch(0.7 0.12 145 / 0.15); color: oklch(0.7 0.12 145)"
					>
						<TargetIcon class="size-5" />
					</div>
					<h3 class="text-base font-bold mb-2">Personalized Goals</h3>
					<p class="text-sm text-muted-foreground leading-relaxed">
						Set calorie and macro targets based on your body and goals, or enter them manually.
					</p>
				</div>

				<div class="rounded-2xl border p-6 shadow-xs dark:bg-input/30">
					<div
						class="size-11 rounded-xl flex items-center justify-center mb-4"
						style="background: oklch(0.75 0.12 85 / 0.15); color: oklch(0.75 0.12 85)"
					>
						<TrendingUpIcon class="size-5" />
					</div>
					<h3 class="text-base font-bold mb-2">Track Progress</h3>
					<p class="text-sm text-muted-foreground leading-relaxed">
						See your calories and macros at a glance. Monitor your weight trend over time.
					</p>
				</div>
			</div>
		</div>
	</section>

	<section id="pricing" class="py-12">
		<div class="container px-4 md:px-6 mx-auto">
			<div class="text-center max-w-2xl mx-auto mb-12">
				<h2 class="text-3xl font-bold tracking-tight sm:text-4xl mb-4">Simple pricing</h2>
				<p class="text-muted-foreground text-lg">Try free for 7 days. Cancel anytime.</p>
			</div>

			<div class="w-full max-w-xs mx-auto space-y-6">
				<div class="flex w-full flex-col gap-6 rounded-2xl border p-6 shadow-xs dark:bg-input/30">
					<div class="space-y-1 text-center">
						<h2 class="text-lg font-bold">Calories Pro</h2>
						<div class="flex items-baseline justify-center gap-1">
							<span class="text-4xl font-bold">$3</span>
							<span class="text-muted-foreground">/month</span>
						</div>
						<p class="text-xs text-muted-foreground">Try free for 7 days</p>
					</div>

					<div class="space-y-3">
						{#each features as feature (feature)}
							<div class="flex items-center gap-3">
								<div class="flex size-5 items-center justify-center rounded-full bg-primary/10">
									<CheckIcon class="size-3 text-primary" />
								</div>
								<span class="text-sm">{feature}</span>
							</div>
						{/each}
					</div>

					<Button class="h-10 w-full" href="{PUBLIC_APP_URL}/signin">Start Free Trial</Button>

					<p class="text-center text-xs text-muted-foreground">
						Secure payment via Stripe. Cancel anytime.
					</p>
				</div>
			</div>
		</div>
	</section>
</main>

<style>
	.perspective-1000 {
		perspective: 1000px;
	}
</style>
