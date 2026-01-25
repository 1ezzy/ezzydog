<script lang="ts">
	import Cauldron from '$lib/components/projects/Cauldron.svelte';
	import Luckball from '$lib/components/projects/Luckball.svelte';

	import flowerprojects from '$lib/assets/flowers/flowerprojects.png';
</script>

<div class="section-wrapper">
	<div class="mb-16 flex flex-row items-center justify-between">
		<h2 id="projects" class="pt-16 text-4xl">My Projects</h2>
	</div>
	<div class="flex h-fit flex-col items-center justify-center gap-48 3xl:gap-96">
		<Luckball />
		<img src={flowerprojects} alt="flower separating projects" class="h-[20vh]" />
		<Cauldron />
	</div>
</div>
