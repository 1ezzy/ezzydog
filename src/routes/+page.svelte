<script>
	import AboutMe from '$lib/components/AboutMe.svelte';
	import HeroSection from '$lib/components/HeroSection.svelte';
</script>

<svelte:head>
	<title>home | ezzy.dog</title>
</svelte:head>

<main class="w-full flex flex-col gap-32 relative">
	<HeroSection />
	<img
		src="images/flower-1.png"
		alt="separating flower"
		class="absolute left-1/2 -translate-x-1/2 top-[100vh] -translate-y-1/2 z-10 w-32"
	/>
	<AboutMe />
</main>
