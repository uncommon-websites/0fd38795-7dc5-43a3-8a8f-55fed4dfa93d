<script lang="ts">
	// Types
	import type { PageProps } from "./$types";

	// Components
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import Pricing from "$lib/components/layout/Pricing.svelte";

	// Props
	const { data }: PageProps = $props();
</script>

<Pricing />

<Testimonials
  testimonials={[
    {
      name: "Lorena Dai",
      position: "Training Supervisor",
      company: "Siemens Energy",
      quote: "With Squint, we cut training time by 40% without adding headcount. It's the easiest tech we’ve rolled out to the floor.",
      image: "/generated/image-a-professional-headshot-of-an-east-asian.webp"
    },
    {
      name: "Marcus Owens",
      position: "Director of Manufacturing",
      company: "CPG Corp",
      quote: "We had tons of videos and Excel docs nobody looked at. Squint made it all usable—and helped us standardize work across shifts.",
      image: "/generated/image-a-professional-headshot-of-an-african-am.webp"
    },
    {
      name: "Tanya Reed",
      position: "Operations Engineer",
      company: "Pall Corporation",
      quote: "Operators now solve issues on their own—in seconds, not minutes. Our downtime went down, and team confidence went way up.",
      image: "/generated/image-a-professional-headshot-of-a-south-asian.webp"
    }
  ]}
/>

<CallToAction
  title="Ready to make every shift run smoother?"
  subtitle="Upgrade your floor instructions with AI-powered workflows."
  description="Squint instantly turns tribal knowledge into standardized step-by-step procedures, so your operators can get more done with less guesswork. See how frontline teams are using Squint to improve productivity, speed up onboarding, and keep every job consistent."
  imageSrc="/generated/image-a-cheerful-manufacturing-worker-smiling-.webp"
  callsToAction={[
    { href: '/demo', label: 'See Squint in action', variant: 'primary' },
    { href: '/contact', label: 'Talk to our team', variant: 'secondary' }
  ]}
/>
