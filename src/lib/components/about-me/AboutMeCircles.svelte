<script lang="ts">
	import { MediaQuery } from 'svelte/reactivity';
	import { ArrowBigDown } from '@lucide/svelte';
	import useEmblaCarousel from 'embla-carousel-svelte';
	import Autoplay from 'embla-carousel-autoplay';
	import type { EmblaOptionsType } from 'embla-carousel';

	import flower2 from '$lib/assets/flower2.png';
	import sveltelogo from '$lib/assets/logos/sveltelogo.svg';
	import tslogo from '$lib/assets/logos/tslogo.svg';
	import tailwindlogo from '$lib/assets/logos/tailwindlogo.svg';
	import pnpmlogo from '$lib/assets/logos/pnpmlogo.svg';

	const large = new MediaQuery('min-width: 1536px');

	const images = [
		{ src: pnpmlogo, alt: 'logo for pnpm', name: 'pnpm' },
		{ src: sveltelogo, alt: 'logo for svelte', name: 'Svelte' },
		{ src: tailwindlogo, alt: 'logo for tailwindcss', name: 'Tailwind CSS' },
		{ src: tslogo, alt: 'logo for typescript', name: 'TypeScript' }
	];

	let emblaApi: any = $state();

	let options: EmblaOptionsType = { loop: true, duration: 25 };
	let plugins = [Autoplay()];

	const onInit = (event: CustomEvent) => {
		emblaApi = event.detail;
		emblaApi.plugins().autoplay?.play();
	};
</script>

<div
	class="relative my-auto flex max-h-400 w-full flex-1 flex-row items-center justify-center overflow-hidden py-8"
>
	<div class="absolute left-0 h-[35vw] max-h-full w-full rounded-full bg-violet-400">
		<div
			class="font-cal flex h-full flex-col items-center justify-center gap-4 pt-12 pr-16 pl-[47vw] 2xl:gap-8 2xl:pt-24 2xl:pr-32"
		>
			<span class="text-md">
				I'm a front-end developer with a passion for building intuitive, robust interfaces and
				tackling complex technical challenges. I love taking on new projects as a way to learn and
				enjoy exploring new ideas by writing code!
			</span>
			<span class="text-md">
				Check out my resume and some of my favorite technologies to the right along with some of the
				projects I have developed below!</span
			>
			<a href="#projects" aria-label="Scroll to Projects" class="text-violet-200">
				<ArrowBigDown size={large ? 64 : 32} />
			</a>
		</div>
	</div>
	<div
		class="absolute left-0 flex aspect-square h-[40vw] max-h-full flex-col items-center justify-start gap-8 rounded-full border-2 border-white bg-violet-300 p-12 2xl:gap-16 2xl:border-4 2xl:p-24"
	>
		<div
			class="font-cal flex aspect-square h-full min-w-0 flex-col items-center justify-center gap-4 2xl:gap-8"
		>
			<div class="flex flex-col items-center pb-4 2xl:pb-8">
				<span class="text-center text-sm text-white">(some of)</span>
				<h2 class="text-center text-4xl text-black">my favorite techs</h2>
			</div>
			<div class="embla max-w-full">
				<div
					class="overflow-hidden"
					onemblaInit={onInit}
					use:useEmblaCarousel={{ options, plugins }}
				>
					<div class="flex touch-pan-y touch-pinch-zoom gap-24">
						{#each images as image (image.src)}
							<div class="flex shrink-0 flex-col items-center gap-8 last:mr-24">
								<img
									src={image.src}
									alt={image.alt}
									class="h-40 w-40 shrink-0"
									loading="eager"
									decoding="sync"
								/>
								<h3 class="text-2xl">{image.name}</h3>
							</div>
						{/each}
					</div>
				</div>
			</div>
		</div>
		<img
			src={flower2}
			alt="separating flower"
			class="absolute top-1/2 -right-[10vw] z-10 w-[10vw] -translate-x-1/2 -translate-y-1/2"
		/>
	</div>
</div>
