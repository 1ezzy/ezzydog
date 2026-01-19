<script>
	import AboutMe from '$lib/components/AboutMe.svelte';
	import HeroSection from '$lib/components/HeroSection.svelte';
</script>

<svelte:head>
	<title>home | ezzy.dog</title>
</svelte:head>

<main class="w-full flex flex-col gap-32">
	<HeroSection />
	<AboutMe />
</main>
