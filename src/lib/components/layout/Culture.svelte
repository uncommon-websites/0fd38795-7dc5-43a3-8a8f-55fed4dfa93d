<script lang="ts">
	import SectionHeader from "$lib/components/layout/SectionHeader.svelte";
	import { animate, stagger } from "motion";
	import { onMount } from "svelte";

	// Types
	export type Value = {
		title: string;
		description: string;
	};

	// Props
	const { values = [
  {
    title: 'Real-world impact',
    description: 'We care about building products that matter—safety, speed, and clarity on the floor always come first.'
  },
  {
    title: 'Low ego, high trust',
    description: 'Frontline experience is the real expert. We listen, we iterate, and we keep our focus on practical results.'
  },
  {
    title: 'Remote, but connected',
    description: 'Our team is distributed but meets in person regularly to share ideas and momentum. Everyone’s voice is heard.'
  },
  {
    title: 'Continuous improvement',
    description: 'We’re always learning—from our customers and each other. No process is sacred and no problem unsolvable.'
  },
  {
    title: 'Work should be fun and focused',
    description: 'Less bureaucracy, more building. We have serious goals, but don’t take ourselves too seriously.'
  }
]: { values: Value[] } = $props();

	let cards: HTMLElement[] = $state([]);

	onMount(() => {
		if (!cards.length) return;
		animate(
			cards,
			{
				y: ["1.5rem", 0],
				filter: ["blur(2px)", "blur(0px)"],
				opacity: [0, 1]
			},
			{
				duration: 0.3,
				ease: "easeOut",
				delay: stagger(0.1, {
					ease: "easeInOut"
				})
			}
		);
	});
</script>

<section class="bg-white dark:bg-gray-950">
	<div
		class="section-py section-px container mx-auto grid gap-8 [--gap:--spacing(8)] [--radius:var(--radius-2xl)]"
	>
		<SectionHeader title="We’re building tools for the people who build everything else" subtitle="The values that shape how we work, every day" />

		<div class="grid gap-(--gap) items-start" style:grid-template-columns="repeat(auto-fit, minmax(280px, 1fr))">
  <img src="/generated/image-a-diverse-group-of-people-in-a-cozy-home.webp" alt="Squint remote team culture" class="rounded-xl w-full h-auto max-w-xs m-auto shadow-lg mb-8" style="grid-row: span 2; grid-column: 1;" />
  {#each values as value, i}
    <div
      bind:this={cards[i]}
      class="relative border-t border-gray-200 pt-4 dark:border-gray-900"
    >
      <!-- Content -->
      <div class="text-caption z-10">
        <div>
          <div class="text-headline mb-[1em]">{value.title}</div>
          <div class="text-body text-gray-500 dark:text-gray-400">{value.description}</div>
        </div>
      </div>
    </div>
  {/each}
</div>
	</div>
</section>
