<script lang="ts">
	import useEmblaCarousel from 'embla-carousel-svelte';
	import Autoplay from 'embla-carousel-autoplay';
	import type { EmblaOptionsType } from 'embla-carousel';

	interface Props {
		images: { src: string; alt: string; description: string }[];
		projectDetails: { name: string; shortDesc: string; longDesc: string };
		techs: { src: string; alt: string; name: string }[];
	}

	let { images, projectDetails, techs }: Props = $props();

	let emblaApi: any = $state();

	let options: EmblaOptionsType = { loop: true, duration: 40, slidesToScroll: 1, align: 'center' };
	let plugins = [Autoplay({ delay: 8000 })];

	const onInit = (event: CustomEvent) => {
		emblaApi = event.detail;
		emblaApi.plugins().autoplay?.play();
	};
</script>

<div class="flex h-[50vh] flex-1 gap-16">
	<div class="h-full min-w-0 flex-1">
		<div class="relative h-full min-w-0">
			<div class="absolute top-2 left-2 h-[50vh] w-full bg-zinc-500"></div>
			<div class="absolute -top-2 -left-2 h-[50vh] w-full bg-violet-300"></div>
			<div class="relative z-10 flex h-full flex-col gap-8 p-8 3xl:gap-16 3xl:p-16">
				<div class="flex basis-1/2 flex-col gap-2 3xl:gap-4">
					<h2 class="text-4xl text-white">{projectDetails.name} - {projectDetails.shortDesc}</h2>
					<span class="font-cal">{projectDetails.longDesc}</span>
				</div>
				<div class="flex basis-1/2 flex-col gap-2 3xl:gap-4">
					<h3 class="text-2xl text-white">Some of the tech involved in this project</h3>
					<div class="flex flex-wrap gap-8 3xl:gap-16">
						{#each techs as tech}
							<div class="flex flex-col items-center justify-center gap-2">
								<img
									src={tech.src}
									alt={tech.alt}
									class="h-16 w-16 object-contain 3xl:h-32 3xl:w-32"
									loading="eager"
									decoding="sync"
								/>
								<span class="font-cal text-sm">{tech.name}</span>
							</div>
						{/each}
					</div>
				</div>
			</div>
		</div>
	</div>
	<div class="aspect-square h-full min-w-0">
		<div class="relative">
			<div class="absolute top-2 left-2 aspect-square h-[50vh] bg-zinc-500"></div>
			<div class="absolute -top-2 -left-2 aspect-square h-[50vh] bg-white"></div>
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
										class="h-48 w-full object-contain 4xl:h-96"
										loading="eager"
										decoding="sync"
									/>
									<span class="font-cal px-4 text-center text-sm">{image.description}</span>
								</div>
							{/each}
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>
