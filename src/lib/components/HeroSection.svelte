<script lang="ts">
	import { onMount } from 'svelte';
	import { MediaQuery } from 'svelte/reactivity';
	import { Tilt } from 'svelte-ux';
	import { ArrowBigDown, CornerLeftUp } from '@lucide/svelte';
	import { intersectionObserverAttachment } from '$lib/utils/attachments';

	import flowers from '$lib/assets/flowers.png';

	let footerEl: Element | undefined = $state();

	const large = new MediaQuery('min-width: 1536px');

	const handleTitleIntersection = (entry: IntersectionObserverEntry) => {
		if (entry.isIntersecting) {
			entry.target.classList.add('opacity-100');
			entry.target.classList.remove('opacity-0');
		} else {
			entry.target.classList.add('opacity-0');
			entry.target.classList.remove('opacity-100');
		}
	};

	const handleFlowersIntersection = (entry: IntersectionObserverEntry) => {
		if (entry.isIntersecting) {
			entry.target.classList.add('opacity-100');
			entry.target.classList.remove('opacity-0');
			footerEl?.classList.add('opacity-100');
			footerEl?.classList.remove('opacity-0');
		} else {
			entry.target.classList.add('opacity-0');
			entry.target.classList.remove('opacity-100');
			footerEl?.classList.add('opacity-0');
			footerEl?.classList.remove('opacity-100');
		}
	};
</script>

<div class="flex min-h-screen">
	<img
		id="flowers"
		src={flowers}
		alt="flowers"
		class="absolute -top-16 object-cover transition duration-600 ease-in-out"
		{@attach intersectionObserverAttachment(handleFlowersIntersection)}
	/>
	<div
		class="absolute top-[calc(100vh-64px)] flex flex-col p-4 opacity-100 transition duration-600 ease-in-out 2xl:top-[calc(100vh-128px)] 2xl:p-8"
		bind:this={footerEl}
	>
		<span class="text-xs">powered by ezzy!</span>
		<span class="text-xs">Images © Wannapa Kaewluan</span>
	</div>
	<div class="flex w-full flex-col items-center justify-center gap-12">
		<div class="relative">
			<Tilt class="transition duration-500 hover:scale-110">
				<h1
					class="font-bagel my-8 w-fit bg-linear-to-r from-violet-300 via-violet-400 to-violet-500 bg-clip-text p-4 text-8xl text-transparent transition ease-out"
					{@attach intersectionObserverAttachment(handleTitleIntersection)}
				>
					ezzy.dog
				</h1>
			</Tilt>
			<div class="absolute bottom-4 left-2/3 flex h-6 items-center gap-2 2xl:h-10">
				<CornerLeftUp size={large ? 16 : 8} />
				<span class="self-end text-xs">(hover me!)</span>
			</div>
		</div>
		<div class="flex w-full flex-col items-center justify-center gap-4">
			<h2 class="text-4xl">a portfolio project by Jordan</h2>

			<h3 class="text-xl">scroll down to learn about me and some of my projects!</h3>
			<a href="#about" aria-label="Scroll to About Me" class="text-violet-400">
				<ArrowBigDown size={large ? 64 : 32} />
			</a>
		</div>
	</div>
</div>

<style>
</style>
