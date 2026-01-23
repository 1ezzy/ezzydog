<script>
	import AboutMe from '$lib/components/AboutMe.svelte';
	import HeroSection from '$lib/components/HeroSection.svelte';
	import Projects from '$lib/components/Projects.svelte';

	import flower1 from '$lib/assets/flower1.png';
	import flower3 from '$lib/assets/flower3.png';
</script>

<svelte:head>
	<title>home | ezzy.dog</title>
</svelte:head>

<main class="relative flex w-full flex-col gap-32">
	<HeroSection />
	<img
		src={flower1}
		alt="separating flower"
		class="absolute top-[100vh] left-1/2 z-10 w-[10vw] -translate-x-1/2 -translate-y-1/2"
	/>
	<AboutMe />
	<img
		src={flower3}
		alt="second separating flower"
		class="absolute top-[calc(215vh)] left-1/2 z-10 w-[10vw] -translate-x-1/2 -translate-y-1/2"
	/>
	<Projects />
</main>
