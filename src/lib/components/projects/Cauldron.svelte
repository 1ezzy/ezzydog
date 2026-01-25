<script lang="ts">
	import ProjectBase from './ProjectBase.svelte';

	import alarm from '$lib/assets/projects/cauldron/alarm.png';
	import spellbook from '$lib/assets/projects/cauldron/spellbook.png';
	import spellbooks from '$lib/assets/projects/cauldron/spellbooks.png';
	import spelltable from '$lib/assets/projects/cauldron/spelltable.png';

	import tslogo from '$lib/assets/logos/ts.svg';
	import sveltelogo from '$lib/assets/logos/svelte.svg';
	import tailwindlogo from '$lib/assets/logos/tailwind.svg';
	import pnpmlogo from '$lib/assets/logos/pnpm.svg';
	import zodlogo from '$lib/assets/logos/zod.svg';
	import mongodblogo from '$lib/assets/logos/mongodb.svg';
	import prismalogo from '$lib/assets/logos/prisma.svg';
	import cloudflareworkerslogo from '$lib/assets/logos/cloudflareworkers.svg';

	const images: { src: string; alt: string; description: string }[] = [
		{
			src: spelltable,
			alt: 'a table of different DND5e spells',
			description:
				'Users can see spells and their details in a centralized table. They can also use the add icon to add spells directly to one of their spellbooks.'
		},
		{
			src: alarm,
			alt: 'a description for a DND spell',
			description:
				'Users can select a spell from their spellbook or the spell table and view its details.'
		},
		{
			src: spellbooks,
			alt: 'a collection of Cauldron spellbooks',
			description:
				'Users can see their spellbooks in one place and select different spellbooks to see different collections of spells, usually for different characters.'
		},
		{
			src: spellbook,
			alt: 'a collection of different level DND5e spells',
			description:
				'Users can see their spellbooks in one place and select different spellbooks to see different collections of spells, usually for different characters.'
		}
	];

	const projectDetails = {
		name: 'Cauldron',
		shortDesc: 'A DND5e Spellbook Generator',
		longDesc:
			'Cauldron streamlines spell management for D&D 5e players. Search and filter the entire spell library, then organize spells into custom spellbooks for each character. All your spell details live on one page, so you can focus on gameplay instead of flipping through rulebooks.',
		url: 'https://github.com/1ezzy/cauldron',
		slug: 'cauldron'
	};

	const techs = [
		{
			src: tslogo,
			alt: 'typescript logo',
			name: 'TypeScript'
		},
		{
			src: sveltelogo,
			alt: 'sveltekit logo',
			name: 'SvelteKit'
		},
		{
			src: tailwindlogo,
			alt: 'tailwindcss logo',
			name: 'TailwindCSS'
		},
		{
			src: zodlogo,
			alt: 'zod logo',
			name: 'Zod'
		},
		{
			src: pnpmlogo,
			alt: 'pnpm logo',
			name: 'pnpm'
		},
		{
			src: mongodblogo,
			alt: 'mongodb logo',
			name: 'MongoDB'
		},
		{
			src: prismalogo,
			alt: 'prisma logo',
			name: 'Prisma'
		},
		{
			src: cloudflareworkerslogo,
			alt: 'cloudflare workers logo',
			name: 'Cloudflare'
		}
	];
</script>

<ProjectBase {images} {projectDetails} {techs} reverse={true} />
