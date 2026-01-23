<script lang="ts">
	import { MediaQuery } from 'svelte/reactivity';
	import Cauldron from '$lib/components/projects/Cauldron.svelte';

	const large = new MediaQuery('min-width: 1536px');
	const xlarge = new MediaQuery('min-width: 2560px');
</script>

<div class="section-wrapper">
	<div class="mb-16 flex flex-row items-center justify-between">
		<h2 id="projects" class="pt-16 text-4xl">My Projects</h2>
	</div>
	<div class="flex h-fit items-center justify-center">
		<Cauldron />
	</div>
</div>
