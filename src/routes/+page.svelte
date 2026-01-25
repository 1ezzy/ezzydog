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

<main class="relative flex w-full flex-col gap-32 3xl:gap-64">
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
		class="absolute top-[calc(200vh+8rem)] left-1/2 z-10 w-[7vw] -translate-x-1/2 -translate-y-1/2 3xl:top-[calc(200vh+16rem)]"
	/>
	<Projects />
</main>
<footer class="flex w-full justify-center p-4 pt-32 pb-8 3xl:pt-64 3xl:pb-16">
	<span>Thanks for visiting!</span>
</footer>
