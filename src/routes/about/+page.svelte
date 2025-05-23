<script lang="ts">
	// Components
	import CallToAction from "$lib/components/layout/CallToAction.svelte";

	// Icons
	import StakeholderGrid from "$lib/components/layout/StakeholderGrid.svelte";
	import Story from "./Story.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";

	// Constants
	const values = [
		{
			title: "Innovation",
			description: "Constantly challenging the status quo to create better solutions."
		},
		{
			title: "Integrity",
			description: "Building trust through transparent actions and honest communication."
		},
		{
			title: "Impact",
			description: "Measuring our success by the positive change we create for our clients."
		}
	];
</script>

<SecondaryHero
	title="Redefining frontline work with AI"
	subtitle="Faster training, safer teams, smarter tools"
	imageSrc="/generated/image-a-diverse-group-of-professionals-collabo.webp"
/>

<!-- Story Section -->
<Story
	paragraphs={[
        "Most industrial teams struggle with a simple but costly problem: the knowledge needed to do the job safely and correctly often lives in someone’s head. It rarely makes it into standardized instructions. Founders Devin Bhushan, Dylan Conway, and Jim Zhu saw firsthand how critical know-how was getting lost—in videos, spreadsheets, inboxes, or retired supervisors. New hires would shadow experienced operators for weeks. And whenever something went wrong on the line, answers were hard to find.",
        "That’s why they built Squint. It uses AI to capture tribal knowledge from fragmented sources—like how-to videos or maintenance checklists—and instantly turns it into clean, step-by-step procedures your team can follow. These aren’t just digital PDFs. Operators get hands-on visual guidance—photos, video clips, and spatial steps—stitched together into one consistent view. What was once learned slowly through trial and error is now accessible in real time. No downloads, no hardware, just real-world help that lives on the devices operators already use.",
        "The goal is simple: better training, safer work, and fewer costly mistakes. Squint makes it easy for teams to do work correctly the first time—and confidently repeat it the next. That’s what drives us: giving every frontline worker an edge, keeping plants productive, and making complex tasks less overwhelming for the people doing them every day."
    ]}
/>

<!-- Our Culture Section -->
<Culture />

<!-- StakeholderGrid Section -->
<StakeholderGrid
  stakeholderType="team"
  title="The team behind Squint."
  subtitle="Meet our founders."
  stakeholders={[
    {
      name: "Devin Bhushan",
      position: "CEO & Founder",
      bio: "Devin built Squint to give frontline workers instant access to everything they need to do great work. Before Squint, Devin led AR and computer vision at enterprise scale at Splunk and Salesforce.",
      image: "/generated/image-a-portrait-of-devin-bhushan-a-ceo-with-a.webp"
    },
    {
      name: "Dylan Conway",
      position: "Founding Customer Lead",
      bio: "Dylan ensures Squint works in the real world—learning directly from teams on the floor and keeping operators in focus. He draws on years supporting digital transformation at manufacturing plants across the U.S.",
      image: "/generated/image-a-portrait-of-dylan-conway-a-customer-le.webp"
    },
    {
      name: "Jim Zhu",
      position: "Founding Architect",
      bio: "Jim designs simple, reliable systems that just work. He’s spent his career engineering scalable platforms for data-driven companies, always pushing for clarity and stability behind the scenes.",
      image: "/generated/image-a-portrait-of-jim-zhu-an-architect-with-.webp"
    }
  ]}
/>




<!-- CTA Section -->
<CallToAction
  title="Passionate about meaningful work?"
  subtitle="We’re always looking for builders and partners"
  description="If you want to help make frontline work safer and smarter or if your company cares about performance in the field—we’d love to connect. Say hello or check out open roles."
  imageSrc="/generated/image-a-diverse-group-of-people-in-a-cozy-home.webp"
  callsToAction={[
    {
      href: "mailto:hello@squint.ai",
      label: "Email us",
      variant: "primary"
    },
    {
      href: "/careers",
      label: "See open roles",
      variant: "secondary"
    }
  ]}
/>
