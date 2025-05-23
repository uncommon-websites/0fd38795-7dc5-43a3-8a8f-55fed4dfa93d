<script lang="ts">
	// Components
	import UseCases from "$lib/components/layout/UseCases.svelte";
	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import AboutTeaser from "$lib/components/layout/AboutTeaser.svelte";
	import LogoScroller from "$lib/components/layout/LogoScroller.svelte";
	import CustomerCardHero from "$lib/components/layout/hero-sections/CustomerCardHero.svelte";
</script>

<CustomerCardHero
  centered={true}
  title="Turn know-how into clear work instructions"
  subtitle="Squint transforms tribal knowledge into standardized, visual procedures—so operators get answers faster, training takes less time, and your floor stays productive."
  customers={[
    {
      name: "Maria Rodriguez",
      position: "Training Coordinator, Equipment Manufacturing",
      imageSrc: "/generated/image-a-female-industrial-training-coordinator.webp"
    },
    {
      name: "Derrick Brooks",
      position: "Assembly Line Supervisor, Manufacturing",
      imageSrc: "/generated/image-a-male-assembly-line-supervisor-standing.webp"
    },
    {
      name: "Emily Chen",
      position: "Plant Manager, Food & Beverage",
      imageSrc: "/generated/image-a-female-food-and-beverage-plant-manager.webp"
    },
    {
      name: "Tom Foster",
      position: "Operations Manager, Energy",
      imageSrc: "/generated/image-a-male-operations-manager-standing-smart.webp"
    },
    {
      name: "Lucas Miller",
      position: "Equipment Technician, Industrial",
      imageSrc: "/generated/image-a-male-equipment-technician-in-safety-ge.webp"
    }
  ]}
/>
<LogoScroller
	label="Trusted by industry leaders"
	logoUrls={[
		'https://logo.clearbit.com/cat.com',
		'https://logo.clearbit.com/pge.com',
		'https://logo.clearbit.com/siemens.com',
		'https://logo.clearbit.com/danone.com'
	]}
/>

<Summary
	title="What we do"
	text="Squint uses AI to turn videos, spreadsheets, and manuals into step-by-step work instructions for industrial teams. Operators get clear, guided help right on the floor. Training gets easier, and procedures stay consistent everywhere."
/>

<Testimonials
	testimonials={[
		{
			name: "Ari Benton",
			position: "Reliability Manager, Tepco Manufacturing",
			company: "Tepco Manufacturing",
			quote: "We trimmed our training time by 30%—freeing up hours every week and getting new operators productive on day one.",
			image: "/generated/image-a-male-reliability-manager-in-a-large-in.webp"
		},
		{
			name: "Niko Kwan",
			position: "Senior Training Supervisor, ClearRiver Energy",
			company: "ClearRiver Energy",
			quote: "We reduced critical errors on the floor with smart step-by-step procedures. Our teams complete advanced tasks with confidence.",
			image: "/generated/image-an-asian-male-senior-training-supervisor.webp"
		},
		{
			name: "Ren Walsh",
			position: "Production Systems Analyst, Nokona Foods",
			company: "Nokona Foods",
			quote: "Squint let us digitize and standardize instructions, saving $72k in quality costs in just six months.",
			image: "/generated/image-a-female-production-systems-analyst-in-a.webp"
		}
	]}
/>

<Features
  title="Features"
  subtitle="Squint covers every step—capture, instruction, guidance, support, insights, and security."
  features={[
    {
      title: "AI transforms old documents and videos",
      description: "Convert spreadsheets, PDFs, and how-to videos into interactive procedures in minutes using Squint's AI."
    },
    {
      title: "Standardized digital work instructions",
      description: "Create and distribute consistent procedures with step-by-step video, image, and text instructions for every task."
    },
    {
      title: "AR-based spatial mapping and guidance",
      description: "Pin instructions, visual markers, and media directly to physical equipment—no QR codes or special hardware required."
    },
    {
      title: "AI-powered on-the-job help",
      description: "Get real-time answers and context-specific guidance from AI, accessible instantly by any operator on the floor."
    },
    {
      title: "Real-time analytics and performance tracking",
      description: "Monitor task completion, identify knowledge gaps, and track performance trends across teams and facilities."
    },
    {
      title: "Secure deployment with SSO and compliance",
      description: "SOC 2 Type II compliant with enterprise-ready login options including single sign-on and badge-based access."
    }
  ]}
/>

<UseCases
	title="Use Cases"
	subtitle="Real-world applications for your business needs"
	useCases={[
		{
			title: "Capture hidden know-how before it’s lost",
			description: "Turn floor videos and expert walkthroughs into searchable, repeatable procedures that anyone can follow.",
			image: "/generated/image-an-industrial-worker-in-a-busy-factory-e.webp",
			link: {
				href: "/use-cases/tribal-knowledge-to-digital-procedures",
				label: "Learn more"
			}
		},
		{
			title: "Guide every step with AR-assistance",
			description: "Give operators live, hands-free visual instructions directly on screens or wearables, right where they work.",
			image: "/generated/image-a-maintenance-technician-in-a-modern-ind.webp",
			link: {
				href: "/use-cases/ar-guided-support",
				label: "Learn more"
			}
		},
		{
			title: "Spot training gaps and raise performance",
			description: "Monitor usage, completion, and timing to uncover quality issues and knowledge gaps by shift, site, or task.",
			image: "/generated/image-a-production-supervisor-in-a-lively-manu.webp",
			link: {
				href: "/use-cases/operator-insight-and-performance",
				label: "Learn more"
			}
		}
	]}
/>

<AboutTeaser />
<CallToAction
  title="The fastest way to get operators up to speed"
  subtitle="Do the job right. First time, every time."
  description="Squint turns know-how into clear instructions your team can use instantly—no delays, no confusion. From routine tasks to urgent fixes, operators follow accurate step-by-step guidance—right where work happens."
  imageSrc="/generated/image-a-joyful-female-industrial-supervisor-st.webp"
  callsToAction={[
    { href: "/get-started", label: "Get started", variant: "primary" },
    { href: "/contact", label: "Talk to sales", variant: "secondary" },
  ]}
/>
