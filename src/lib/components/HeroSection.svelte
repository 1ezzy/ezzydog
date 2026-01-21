<script lang="ts">
	import { onMount } from 'svelte';
	import { MediaQuery } from 'svelte/reactivity';
	import { Tilt } from 'svelte-ux';
	import { ArrowBigDown } from '@lucide/svelte';
	import { intersectionObserverAttachment } from '$lib/utils/attachments';

	import flowers from '$lib/assets/flowers.png';

	let mounted = $state(false);
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

	onMount(() => {
		mounted = true;
	});
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
		<Tilt class="transition duration-500 hover:scale-110">
			<h1
				class="font-bagel my-8 w-fit bg-linear-to-r from-violet-300 via-violet-400 to-violet-500 bg-clip-text p-4 text-8xl text-transparent transition duration-600 ease-in-out"
				class:opacity-100={mounted}
				class:opacity-0={!mounted}
				{@attach intersectionObserverAttachment(handleTitleIntersection)}
			>
				ezzy.dog
			</h1>
		</Tilt>
		<div class="flex w-full flex-col items-center justify-center gap-4">
			<h2 class="text-4xl">a portfolio project by Jordan</h2>

			<h3 class="text-xl">scroll down to learn about me and some of my projects!</h3>
			<a href="#about" aria-label="Scroll to About Me" class="text-violet-400">
				<ArrowBigDown size={large ? 64 : 32} />
			</a>
		</div>
	</div>
</div>
