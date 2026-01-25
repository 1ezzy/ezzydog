<script lang="ts">
	import ProjectBase from './ProjectBase.svelte';

	import luckballjoin from '$lib/assets/projects/luckball/luckballjoin.png';
	import luckballschedule from '$lib/assets/projects/luckball/luckballschedule.png';
	import luckballstats from '$lib/assets/projects/luckball/luckballstats.png';

	import tslogo from '$lib/assets/logos/ts.svg';
	import sveltelogo from '$lib/assets/logos/svelte.svg';
	import tailwindlogo from '$lib/assets/logos/tailwind.svg';
	import drizzlelogo from '$lib/assets/logos/drizzle.svg';
	import lucialogo from '$lib/assets/logos/lucia.svg';
	import dockerlogo from '$lib/assets/logos/docker.svg';
	import nginxlogo from '$lib/assets/logos/nginx.svg';
	import digitaloceanlogo from '$lib/assets/logos/digitalocean.svg';

	const images: { src: string; alt: string; description: string }[] = [
		{
			src: luckballjoin,
			alt: 'form to join a week of luckball',
			description:
				'Users can enter their name and join a week of Luckball. After joining, wait until the week starts, where they are auto assigned a random Luckball team with 16 NFL teams.'
		},
		{
			src: luckballschedule,
			alt: 'a schedule for a week of NFL football',
			description:
				'Once the week starts, users get a random team assignment, and that team will contain 16 NFL teams for the player to root for during the week.'
		},
		{
			src: luckballstats,
			alt: 'a users Luckball play stats',
			description:
				'Users can see how many times their team outscored the other team along with their highest scoring team of all time.'
		}
	];

	const projectDetails = {
		name: 'Luckball',
		shortDesc: 'A Weekly Football Team Randomizer',
		longDesc:
			"Luckball transforms NFL weekly matchups into a fantasy-style competition. Each week, the app randomly assigns one team from every matchup to two competing sides. As real games unfold, your side's score combines points from all your assigned teams, and the highest total wins. It's a fresh way to stay invested in every game and compete with friends each NFL Sunday.",
		url: 'https://github.com/1ezzy/luckball',
		slug: 'luckball'
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
			src: drizzlelogo,
			alt: 'drizzle ORM logo',
			name: 'Drizzle'
		},
		{
			src: lucialogo,
			alt: 'lucia auth logo',
			name: 'Lucia'
		},
		{
			src: dockerlogo,
			alt: 'docker logo',
			name: 'Docker'
		},
		{
			src: nginxlogo,
			alt: 'nginx logo',
			name: 'nginx'
		},
		{
			src: digitaloceanlogo,
			alt: 'digital ocean logo',
			name: 'DigitalOcean'
		}
	];
</script>

<ProjectBase {images} {projectDetails} {techs} reverse={false} />
