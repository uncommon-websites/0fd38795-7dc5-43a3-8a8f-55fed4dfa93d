<!--
@component Pricing

Please update features according to the company's product offering. Do not remove this comment.
-->
<script lang="ts">
	// Types
	type PricingTier = {
		name: string;
		monthlyPrice?: number | null;
		yearlyPrice?: number | null;
		description: string;
		features: string[];
		cta: {
			label: string;
			href: string;
		};
		highlight?: boolean;
	};

	type PricingFeature = {
		name: string;
		tiers: {
			[key: string]: boolean | string;
		};
	};

	// Components
	import Button from "$lib/components/ui/Button.svelte";
	import SectionHeader from "./SectionHeader.svelte";
	import IconCheck from "~icons/lucide/check";
	import IconX from "~icons/lucide/x";
	import NumberFlow from "@number-flow/svelte";
	import LogoScroller from "./LogoScroller.svelte";

	// Props
	const {
		title = "Simple, transparent pricing",
		subtitle = "Choose the plan that works best for your needs",
		tierNames = ["Essentials", "Professional", "Enterprise"],
		features = [
			{
				name: "Included procedures",
				tiers: {
					Essentials: "Up to 100",
					Professional: "Unlimited",
					Enterprise: "Unlimited"
				}
			},
			{
				name: "Included users/operators",
				tiers: {
					Essentials: "Up to 50",
					Professional: "Up to 500",
					Enterprise: "Unlimited"
				}
			},
			{
				name: "AI video-to-procedure conversion",
				tiers: {
					Essentials: true,
					Professional: true,
					Enterprise: true
				}
			},
			{
				name: "Spatial equipment guidance",
				tiers: {
					Essentials: false,
					Professional: true,
					Enterprise: true
				}
			},
			{
				name: "Digital data capture (photos, forms, audio)",
				tiers: {
					Essentials: true,
					Professional: true,
					Enterprise: true
				}
			},
			{
				name: "Basic usage analytics",
				tiers: {
					Essentials: true,
					Professional: true,
					Enterprise: true
				}
			},
			{
				name: "Advanced reporting & dashboards",
				tiers: {
					Essentials: false,
					Professional: true,
					Enterprise: true
				}
			},
			{
				name: "Compliance-ready exports",
				tiers: {
					Essentials: false,
					Professional: true,
					Enterprise: true
				}
			},
			{
				name: "Integration support (CMMS, ERP)",
				tiers: {
					Essentials: false,
					Professional: "Standard integrations",
					Enterprise: "Full integration services"
				}
			},
			{
				name: "Single sign-on",
				tiers: {
					Essentials: false,
					Professional: true,
					Enterprise: true
				}
			},
			{
				name: "Multi-factor authentication",
				tiers: {
					Essentials: false,
					Professional: true,
					Enterprise: true
				}
			},
			{
				name: "Enterprise security & audits",
				tiers: {
					Essentials: false,
					Professional: "SOC 2 Type II",
					Enterprise: "SOC 2 Type II + custom security requirements"
				}
			},
			{
				name: "Priority support",
				tiers: {
					Essentials: "Email only",
					Professional: "Priority response",
					Enterprise: "Dedicated success manager"
				}
			},
			{
				name: "Deployment options",
				tiers: {
					Essentials: "Hosted only",
					Professional: "Hosted with optional sandboxes",
					Enterprise: "Custom deployment options available"
				}
			}
		],
		tiers = [
			{
				name: "Essentials",
				monthlyPrice: null,
				yearlyPrice: 15000,
				description: "Digitize tribal knowledge and share clear procedures fast.",
				features: [
					"Up to 100 procedures",
					"Up to 50 users/operators",
					"AI video-to-procedure conversion",
					"Digital data capture (photos, forms, audio)",
					"Basic usage analytics",
					"Email support"
				],
				cta: {
					label: "Start with Essentials",
					href: "/contact-sales"
				}
			},
			{
				name: "Professional",
				monthlyPrice: null,
				yearlyPrice: null,
				description: "Everything in Essentials plus advanced controls, reporting, and integrations.",
				features: [
					"Unlimited procedures",
					"Up to 500 users/operators",
					"Spatial equipment guidance",
					"Advanced reporting & dashboards",
					"Compliance-ready exports",
					"Integration support (CMMS, ERP)",
					"Single sign-on & multi-factor authentication",
					"SOC 2 Type II security",
					"Priority support"
				],
				cta: {
					label: "Request a demo",
					href: "/contact-sales"
				},
				highlight: true
			},
			{
				name: "Enterprise",
				monthlyPrice: null,
				yearlyPrice: null,
				description: "Built for fully integrated rollouts across complex sites and teams.",
				features: [
					"Unlimited procedures & users",
					"Custom integration services",
					"SOC 2 Type II + custom security requirements",
					"Dedicated success manager",
					"Custom deployment options",
					"Full feature set"
				],
				cta: {
					label: "Contact sales",
					href: "/contact-sales"
				}
			}
		]
	}: {
		title?: string;
		subtitle?: string;
		tiers?: PricingTier[];
		features?: PricingFeature[];
		tierNames?: string[];
		caption?: string;
	} = $props();

	// State
	let annual = $state(true);
</script>

<section class="section-py section-px container mx-auto">
	<div class="flex flex-col items-baseline justify-between lg:flex-row">
		<SectionHeader {title} {subtitle} />

		<div class="mb-8 flex justify-center">
			<div class="inline-flex items-center rounded-full bg-gray-100 p-0.5 dark:bg-gray-800">
				<Button
					variant="ghost"
					size="sm"
					class=" {!annual ? 'bg-white shadow-sm dark:bg-gray-700' : ''}"
					onclick={() => (annual = false)}
				>
					Monthly
				</Button>
				<Button
					variant="ghost"
					size="sm"
					rounded
					class={annual ? "bg-white shadow-sm dark:bg-gray-700" : ""}
					onclick={() => (annual = true)}
				>
					Annual <span class="text-primary-600 dark:text-primary-400 text-footnote">Save 20%</span>
				</Button>
			</div>
		</div>
	</div>

	<div class="bb grid gap-6 md:grid-cols-2 lg:grid-cols-3">
		{#each tiers as tier}
			<div
				class="flex flex-col rounded-xl bg-white p-6 ring ring-gray-200 transition-all duration-300 dark:bg-gray-800 dark:ring-gray-700"
				class:ring-2={tier.highlight}
				class:ring-primary={tier.highlight}
				class:dark:ring-primary-700={tier.highlight}
				class:translate-y-[-4px]={tier.highlight}
			>
				<div class="mb-8">
					<h3 class="text-title3 mb-4 dark:text-white">{tier.name}</h3>
					<div class="mt-2 flex items-baseline">
						{#if tier.monthlyPrice === null && tier.yearlyPrice === null}
							<span class="text-title2 dark:text-white">Custom</span>
						{:else}
							<NumberFlow
								class="text-title2 [&::part\(suffix\)]:text-caption dark:text-white"
								format={{
									style: "currency",
									currency: "USD",
									trailingZeroDisplay: "stripIfInteger"
								}}
								value={annual ? tier.yearlyPrice : tier.monthlyPrice}
								suffix="/month"
							/>
						{/if}
					</div>
					<p class="text-callout text-emphasis-medium mt-3 dark:text-gray-300">
						{tier.description}
					</p>
				</div>

				<div class="mb-8 flex-grow">
					<ul class="space-y-3">
						{#each tier.features as feature}
							<li class="flex items-center gap-2">
								<IconCheck class="text-primary-600 dark:text-primary-400 size-5 flex-shrink-0" />
								<span class="text-body text-emphasis-medium dark:text-gray-300">{feature}</span>
							</li>
						{/each}
					</ul>
				</div>

				<div class="mt-auto">
					<Button
						href={tier.cta.href}
						variant={tier.highlight ? "primary" : "secondary"}
						class="w-full"
					>
						{tier.cta.label}
					</Button>
				</div>
			</div>
		{/each}
	</div>
	<div class="mt-32">
		<!-- Responsive table wrapper with horizontal scroll on mobile -->
		<!-- <div class=" hidden overflow-x-auto px-4 sm:mx-0 sm:block sm:px-0">
			<table
				class="w-full min-w-full border-separate border-spacing-0 border-gray-200 text-left dark:border-gray-700"
			>
				<thead>
					<tr>
						<th
							class="sticky left-0 min-w-[120px] border-b border-gray-200 bg-white dark:border-gray-700 dark:bg-gray-900"
						>
							<span class="sr-only">Feature</span>
						</th>
						{#each tierNames as tierName}
							<th
								class="text-headline min-w-[100px] border-b border-gray-200 p-4 text-start font-normal dark:border-gray-700"
							>
								{tierName}
							</th>
						{/each}
					</tr>
				</thead>
				<tbody>
					{#each features as feature}
						<tr>
							<td class="text-caption">
								{feature.name}
							</td>
							{#each tierNames as tierName}
								<td
									class="min-w-[100px] border-b border-gray-200 p-4 text-start text-gray-600 dark:border-gray-700 dark:text-gray-300"
								>
									{#if typeof feature.tiers[tierName] === "boolean"}
										{#if feature.tiers[tierName]}
											<IconCheck
												class="text-primary-600 dark:text-primary-400 mx-auto size-5 sm:mx-0"
											/>
										{:else}
											<IconX class="mx-auto size-5 text-gray-400 sm:mx-0" />
										{/if}
									{:else}
										{feature.tiers[tierName]}
									{/if}
								</td>
							{/each}
						</tr>
					{/each}
				</tbody>
			</table>
		</div> -->

		<!-- Mobile feature comparison (alternative view for very small screens) -->
		<div>
			<!-- Universal pricing comparison for mobile -->
			<div class="overflow-x-auto">
				<table class="w-full border-collapse">
					<!-- Sticky header with tier names -->
					<thead class="border-border sticky top-0 z-10 border-b">
						<tr>
							<th class="min-w-[120px] py-3 text-left">
								<span class="sr-only">Feature</span>
							</th>
							{#each tierNames as tierName, i}
								<th class="text-caption min-w-[100px] py-3 text-left dark:text-white">
									{tierName}
								</th>
							{/each}
						</tr>
					</thead>
					<tbody class="divide-border divide-y">
						{#each features as feature}
							<tr>
								<td class="text-body py-3 pr-8 font-medium lg:pr-0 dark:text-white">
									{feature.name}
								</td>
								{#each tierNames as tierName, i}
									<td class="py-3">
										{#if typeof feature.tiers[tierName] === "boolean"}
											{#if feature.tiers[tierName]}
												<IconCheck class="text-primary-900 dark:text-primary-400 size-5" />
											{:else}
												<IconX class="size-5 text-gray-400" />
											{/if}
										{:else}
											<span class="text-callout font-medium text-gray-700 dark:text-gray-300">
												{feature.tiers[tierName]}
											</span>
										{/if}
									</td>
								{/each}
							</tr>
						{/each}
					</tbody>
				</table>
			</div>
		</div>
	</div>
	<LogoScroller />
</section>

<style lang="postcss">
	@reference '../../../app.css';

	:global(number-flow-svelte)::part(suffix) {
		@apply text-sm text-gray-400 dark:text-gray-500;
	}
</style>
