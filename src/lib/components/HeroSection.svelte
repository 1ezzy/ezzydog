<script lang="ts">
	import { MediaQuery } from 'svelte/reactivity';
	import { Tilt } from 'svelte-ux';
	import { ArrowBigDown, CornerLeftUp } from '@lucide/svelte';
	import { intersectionObserverAttachment } from '$lib/utils/attachments';

	import flowers from '$lib/assets/flowers/flowers.png';

	let footerEl: Element | undefined = $state();

	const large = new MediaQuery('min-width: 1536px');
	const xlarge = new MediaQuery('min-width: 2560px');

	let pointingArrowSize = $derived(() => (xlarge.current ? 24 : large.current ? 18 : 12));
	let arrowSize = $derived(() => (xlarge.current ? 64 : large.current ? 48 : 32));

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
		class="absolute top-[calc(100vh-64px)] flex flex-col p-4 opacity-100 transition duration-600 ease-in-out 3xl:top-[calc(100vh-128px)] 3xl:p-8"
		bind:this={footerEl}
	>
		<span class="text-xs">powered by ezzy!</span>
		<span class="text-xs">Images © Wannapa Kaewluan</span>
	</div>
	<div class="flex w-full flex-col items-center justify-center gap-12">
		<div class="relative">
			<Tilt class="cursor-pointer transition duration-500 hover:scale-110">
				<h1
					class="font-bagel my-8 w-fit bg-linear-to-r from-violet-300 via-violet-400 to-violet-500 bg-clip-text p-4 text-8xl text-transparent transition ease-out 3xl:my-16"
					{@attach intersectionObserverAttachment(handleTitleIntersection)}
				>
					ezzy.dog
				</h1>
			</Tilt>
			<div class="absolute bottom-4 left-2/3 flex h-6 items-center gap-2 3xl:h-10">
				<CornerLeftUp size={pointingArrowSize()} />
				<span class="self-end text-xs">(hover me!)</span>
			</div>
		</div>
		<div class="flex w-full flex-col items-center justify-center gap-2">
			<h2 class="text-4xl">a portfolio project by Jordan</h2>

			<h3 class="text-xl">click the arrow to learn more about me and some of my projects!</h3>
			<a
				href="#about"
				aria-label="Scroll to About Me"
				class="mt-4 flex animate-pulse items-center rounded-full p-2 text-violet-400 hover-fade-in hover:animate-none hover:bg-violet-400 hover:text-white 3xl:mt-8 3xl:p-4"
			>
				<ArrowBigDown size={arrowSize()} />
			</a>
		</div>
	</div>
</div>
