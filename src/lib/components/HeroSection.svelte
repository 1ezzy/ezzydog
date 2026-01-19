<script lang="ts">
	import { onMount } from 'svelte';
	import { fade } from 'svelte/transition';
	import { ArrowBigDown } from '@lucide/svelte';

	let mounted = $state(false);

	onMount(() => {
		mounted = true;
	});
</script>

<div class="flex min-h-screen">
	<img src="images/flowers.png" alt="flowers" class="object-cover absolute -top-16" />
	<div class="w-full flex flex-col items-center justify-center gap-12">
		{#if mounted}
			<h1
				class="text-8xl font-bagel bg-linear-to-r from-violet-300 via-violet-400 to-violet-500 bg-clip-text text-transparent p-4 my-8"
				in:fade={{ duration: 500, delay: 50 }}
			>
				ezzy.dog
			</h1>
		{:else}
			<h1 class="text-8xl font-bagel p-4 invisible my-8">ezzy.dog</h1>
		{/if}
		<div class="w-full flex flex-col items-center justify-center gap-4">
			<h2 class="text-4xl">a portfolio project by Jordan</h2>

			<h3 class="text-xl">scroll down to learn about me and some of my projects!</h3>
			<a href="#about" aria-label="Scroll to About Me" class="text-violet-400">
				<ArrowBigDown />
			</a>
		</div>
	</div>
</div>
