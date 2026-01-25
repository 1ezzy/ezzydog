<script lang="ts">
	import { MediaQuery } from 'svelte/reactivity';
	import { Shine } from 'svelte-ux';
	import useEmblaCarousel from 'embla-carousel-svelte';
	import Autoplay from 'embla-carousel-autoplay';
	import type { EmblaOptionsType } from 'embla-carousel';

	import flower4 from '$lib/assets/flowers/flower4.png';
	import { Github } from '@lucide/svelte';

	const large = new MediaQuery('min-width: 1536px');
	const xlarge = new MediaQuery('min-width: 2560px');

	interface Props {
		images: { src: string; alt: string; description: string }[];
		projectDetails: {
			name: string;
			shortDesc: string;
			longDesc: string;
			url: string;
			slug: string;
		};
		techs: { src: string; alt: string; name: string }[];
		reverse: boolean;
	}

	let { images, projectDetails, techs, reverse }: Props = $props();

	let emblaApi: any = $state();
	let purpleWidth: number | undefined = $state();
	const iconSize = $derived(() => (xlarge.current ? 32 : large.current ? 24 : 16));

	let options: EmblaOptionsType = { loop: true, duration: 40, slidesToScroll: 1, align: 'center' };
	let plugins = [Autoplay({ delay: 8000 })];

	const onInit = (event: CustomEvent) => {
		emblaApi = event.detail;
		emblaApi.plugins().autoplay?.play();
	};
</script>

{#snippet purpleRectangle()}
	<div class="flex-1">
		<div class="relative min-w-0">
			<div
				class="absolute top-2 h-[40vh] w-full bg-violet-400"
				class:left-2={!reverse}
				class:-left-2={reverse}
			></div>
			<div
				class="absolute -top-2 h-[40vh] w-full bg-violet-300"
				class:-left-2={!reverse}
				class:left-2={reverse}
				bind:clientWidth={purpleWidth}
			></div>
			<div
				class="relative z-10 flex h-[40vh] flex-col gap-8 p-8 3xl:gap-12 3xl:p-12 4xl:gap-16 4xl:p-16"
			>
				<div class="flex flex-1 basis-1/2 flex-col gap-4 3xl:gap-8">
					<div class="flex flex-row items-center gap-2 3xl:gap-4">
						<h2 class="text-4xl text-white">{projectDetails.name}</h2>
						<span class="text-2xl text-white"> - </span>
						<h3 class="text-2xl text-white">{projectDetails.shortDesc}</h3>
					</div>
					<span class="font-cal text-sm">{projectDetails.longDesc}</span>
					<div
						class="mt-auto flex items-center justify-between gap-8 3xl:gap-16"
						class:flex-row-reverse={reverse}
					>
						<a
							href={projectDetails.url}
							class="flex items-center justify-center gap-3 rounded-full bg-violet-400 p-4 hover-fade-in hover:bg-violet-500 3xl:gap-6 3xl:p-6 4xl:p-8"
						>
							<Github size={iconSize()} />
							<span class="text-sm">View on GitHub</span>
						</a>
						<div class="flex flex-row gap-4 3xl:gap-8">
							<img
								alt="GitHub Created At"
								src="https://img.shields.io/github/created-at/1ezzy/{projectDetails.slug}?style=flat-square&logo=github&logoSize=auto"
								class="h-4 3xl:h-8 4xl:h-12"
							/>
							<img
								alt="GitHub commit activity"
								src="https://img.shields.io/github/commit-activity/t/1ezzy/{projectDetails.slug}?style=flat-square&logo=github&logoSize=auto"
								class="h-4 3xl:h-8 4xl:h-12"
							/>
							<img
								alt="GitHub language count"
								src="https://img.shields.io/github/languages/count/1ezzy/{projectDetails.slug}?style=flat-square&logo=github&logoSize=auto"
								class="h-4 3xl:h-8 4xl:h-12"
							/>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
{/snippet}

{#snippet whiteSquare()}
	<div class="aspect-square">
		<div class="relative aspect-square max-h-[50vh]">
			<div
				class="absolute top-2 aspect-square h-[50vh] bg-zinc-400"
				class:left-2={!reverse}
				class:-left-2={reverse}
			></div>
			<div
				class="absolute -top-2 aspect-square h-[50vh] bg-white"
				class:-left-2={!reverse}
				class:left-2={reverse}
			></div>
			<div class="relative z-10 flex aspect-square items-center justify-center">
				<div class="embla max-w-full px-12 3xl:px-24">
					<div
						class="overflow-hidden"
						onemblaInit={onInit}
						use:useEmblaCarousel={{ options, plugins }}
					>
						<div class="flex w-full touch-pan-y touch-pinch-zoom">
							{#each images as image (image.src)}
								<div class="flex w-full shrink-0 flex-col items-center justify-center gap-8">
									<img
										src={image.src}
										alt={image.alt}
										class="h-48 max-h-48 w-full basis-1/2 object-contain 4xl:h-96 4xl:max-h-96"
										loading="eager"
										decoding="sync"
									/>
									<span class="font-cal basis-1/2 px-4 text-center text-sm">
										{image.description}
									</span>
								</div>
							{/each}
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
{/snippet}

{#snippet darkPurpleBoxes()}
	<div class="max-w-full flex-1">
		<div class="relative h-full max-w-full min-w-0">
			<div
				class="absolute top-2 h-[20vh] w-full bg-purple-400"
				class:left-2={!reverse}
				class:-left-2={reverse}
			></div>
			<div
				class="absolute -top-2 h-[20vh] w-full bg-purple-300"
				class:-left-2={!reverse}
				class:left-2={reverse}
			>
				<div
					class="absolute -top-[calc(10vh-8px)] h-[10vh] w-full bg-purple-400"
					class:left-4={!reverse}
					class:right-4={reverse}
					style={`width: ${purpleWidth}px`}
				></div>
				<div
					class="absolute -top-[10vh] h-[10vh] w-full bg-purple-300"
					class:right-0={reverse}
					style={`width: ${purpleWidth}px`}
				>
					<div class="flex h-full items-center justify-between px-6 py-4 3xl:px-12 3xl:py-8">
						<h3 class="text-2xl text-white">Project Tools</h3>
						<img class="w-10" src={flower4} alt="header flower" />
					</div>
				</div>
			</div>
			<div
				class="relative z-10 flex h-[20vh] flex-col gap-8 px-8 py-4 3xl:gap-16 3xl:px-12 3xl:py-6 4xl:px-16 4xl:py-8"
			>
				<div class="flex h-full flex-col gap-4 3xl:gap-8">
					<div
						class="flex h-full w-full gap-4 3xl:gap-6 4xl:gap-8"
						class:justify-start={!reverse}
						class:justify-end={reverse}
					>
						{#each techs as tech}
							<div
								class="flex aspect-square h-full max-h-full w-full min-w-0 flex-col items-center justify-center gap-2 overflow-hidden 4xl:h-70"
							>
								<Shine>
									<img
										src={tech.src}
										alt={tech.alt}
										class="h-16 w-16 object-contain 3xl:h-24 3xl:w-24 4xl:h-32 4xl:w-32"
										loading="eager"
										decoding="sync"
									/>
								</Shine>
								<span class="font-cal max-h-5 text-center text-sm 3xl:max-h-10">
									{tech.name}
								</span>
							</div>
						{/each}
					</div>
				</div>
			</div>
		</div>
	</div>
{/snippet}

<div class="flex max-w-full flex-auto flex-col gap-14 3xl:gap-28">
	<div class="flex h-fit min-h-0 gap-16 3xl:gap-32" class:flex-row-reverse={reverse}>
		{@render purpleRectangle()}
		{@render whiteSquare()}
	</div>
	<div class="flex h-full min-h-0 flex-1">
		{@render darkPurpleBoxes()}
	</div>
</div>
