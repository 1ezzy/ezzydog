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
	const xlarge = new MediaQuery('min-width: 2560px');

	const arrowSize = $derived(() => (xlarge.current ? 64 : large.current ? 48 : 32));

	const images: { src: string; alt: string; name: string }[] = [
		{ src: pnpmlogo, alt: 'logo for pnpm', name: 'pnpm' },
		{ src: sveltelogo, alt: 'logo for svelte', name: 'Svelte' },
		{ src: tailwindlogo, alt: 'logo for tailwindcss', name: 'Tailwind CSS' },
		{ src: tslogo, alt: 'logo for typescript', name: 'TypeScript' }
	];

	let emblaApi: any = $state();

	let options: EmblaOptionsType = { loop: true, duration: 25, slidesToScroll: 1, align: 'center' };
	let plugins = [Autoplay()];

	const onInit = (event: CustomEvent) => {
		emblaApi = event.detail;
		emblaApi.plugins().autoplay?.play();
	};
</script>

<div
	class="relative my-auto flex max-h-400 w-full flex-1 flex-row items-center justify-center overflow-hidden py-8"
>
	<div
		class="absolute left-0 flex h-[35vw] max-h-full w-full items-center justify-center rounded-full bg-violet-400"
	>
		<span class="basis-1/2"></span>
		<div
			class="flex h-full basis-1/2 flex-col items-center justify-between py-10 pr-24 pl-8 3xl:max-w-7/8 3xl:gap-8 3xl:px-16 3xl:py-20 3xl:pr-48"
		>
			<span class="flex-1"></span>
			<div class="font-cal flex flex-col items-center gap-4">
				<span class="text-md text-center">
					I'm a front-end developer with a passion for building intuitive, robust interfaces and
					tackling complex technical challenges. I love taking on new projects as a way to learn and
					enjoy exploring new ideas by writing code!
				</span>
				<span class="text-md text-center">
					Feel free to check out my resume and socials above, some of my favorite technologies to
					the left, and some of the projects I have developed below!</span
				>
			</div>
			<a
				href="#projects"
				aria-label="Scroll to Projects"
				class="flex flex-1 items-center justify-center"
			>
				<span
					class="animate-pulse rounded-full p-2 text-white hover-fade-in hover:animate-none hover:bg-violet-300 3xl:p-4"
				>
					<ArrowBigDown size={arrowSize()} />
				</span>
			</a>
		</div>
	</div>
	<div
		class="absolute left-0 flex aspect-square h-[40vw] max-h-full flex-col items-center justify-start gap-8 rounded-full border-2 border-white bg-violet-300 p-12 3xl:gap-16 3xl:border-4 3xl:p-24"
	>
		<div
			id="foobar"
			class="font-cal flex aspect-square h-full min-w-0 flex-col items-center justify-center gap-4 3xl:gap-8 4xl:gap-16"
		>
			<div class="flex flex-col items-center pb-4 3xl:pb-8">
				<span class="text-center text-sm text-white">(some of)</span>
				<h2 class="text-center text-4xl text-black">my favorite techs</h2>
			</div>
			<div class="embla max-w-full px-16 3xl:px-32">
				<div
					class="overflow-hidden"
					onemblaInit={onInit}
					use:useEmblaCarousel={{ options, plugins }}
				>
					<div class="flex w-full touch-pan-y touch-pinch-zoom">
						{#each images as image (image.src)}
							<div class="flex w-full shrink-0 flex-col items-center gap-8">
								<img
									src={image.src}
									alt={image.alt}
									class="h-48 w-full object-contain 4xl:h-96"
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
			class="absolute top-1/2 -right-[7vw] z-10 w-[7vw] -translate-x-1/2 -translate-y-1/2"
			src={flower2}
			alt="separating flower"
		/>
	</div>
</div>
