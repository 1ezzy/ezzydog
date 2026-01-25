<script lang="ts">
	import ProjectBase from './ProjectBase.svelte';

	import luckballjoin from '$lib/assets/projects/luckball/luckballjoin.png';
	import luckballschedule from '$lib/assets/projects/luckball/luckballschedule.png';
	import luckballstats from '$lib/assets/projects/luckball/luckballstats.png';

	import tslogo from '$lib/assets/logos/ts.svg';
	import sveltelogo from '$lib/assets/logos/svelte.svg';

	const images: { src: string; alt: string; description: string }[] = [
		{
			src: luckballjoin,
			alt: 'form to join a week of luckball',
			description:
				'Users can enter their name and join a week of Luckball. After Joining, wait until the week starts, where they are auto assigned a random Luckball team with 16 NFL teams.'
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
			'Luckball is an application that sorts matchups from each week of the National Football League schedule across two randomized teams. Each team in Luckball contains one NFL team from each matchup for the week, and teams in Luckball score as their NFL teams score. The Luckball team with the highest combined score wins the week! This app is a great way to compete with your friends and always ensures you have a team to root for and bet on.',
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
		}
	];
</script>

<ProjectBase {images} {projectDetails} {techs} reverse={false} />
