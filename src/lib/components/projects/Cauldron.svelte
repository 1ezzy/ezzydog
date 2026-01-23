<script lang="ts">
	import ProjectBase from './ProjectBase.svelte';

	import alarm from '$lib/assets/projects/cauldron/alarm.png';
	import spellbook from '$lib/assets/projects/cauldron/spellbook.png';
	import spellbooks from '$lib/assets/projects/cauldron/spellbooks.png';
	import spelltable from '$lib/assets/projects/cauldron/spelltable.png';

	import tslogo from '$lib/assets/logos/tslogo.svg';
	import sveltelogo from '$lib/assets/logos/sveltelogo.svg';
	import mongodblogo from '$lib/assets/logos/mongodblogo.svg';
	import prismalogo from '$lib/assets/logos/prismalogo.svg';

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
			"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged."
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
			src: mongodblogo,
			alt: 'mongodb logo',
			name: 'MongoDB'
		},
		{
			src: prismalogo,
			alt: 'prisma logo',
			name: 'Prisma'
		}
	];
</script>

<ProjectBase {images} {projectDetails} {techs} />
