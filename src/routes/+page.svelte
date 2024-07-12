<script lang="ts">
	import guitar from '$lib/images/guitar.png';
	import alarm from '$lib/images/alarm.png';
	import spellbook from '$lib/images/spellbook.png';
	import cards from '$lib/images/cards.png';
	import band from '$lib/images/band.png';
	import photos from '$lib/images/photos.png';
</script>

<svelte:head>
	<title>ezzydog</title>
</svelte:head>

<main class="w-full md:p-10 p-2 flex flex-col flex-1 md:gap-8 gap-16">
	<section class="h-[calc(100lvh_-_40px)] flex md:flex-row flex-col items-center justify-center">
		<img
			class="w-full md:max-w-lg max-w-1/2 aspect-square md:basis-1/2"
			src={guitar}
			alt="ezzy playing guitar"
		/>
		<div
			class="md:h-2/3 h-1/2 flex flex-col items-center justify-center basis-1/2 md:gap-16 gap-10"
		>
			<div>
				<p class="text-start text-[#ffb1b1] leading-3">welcome to</p>
				<h1 class="text-5xl tracking-wider text-[#ffb1b1] underline decoration-wavy">ezzy.dog</h1>
			</div>
			<div class="gap-4 md:text-center text-start flex flex-col items-center">
				<p class="w-2/3 tracking-wide leading-relaxed">
					Hey there! I'm Ezra, a web developer passionate about all things front-end and full-stack.
				</p>
				<p class="w-2/3 tracking-wide leading-relaxed">
					Below you can find some of the projects I've worked on and some of the technologies I love
					using in my stack. Thanks for checking me out!
				</p>
			</div>
		</div>
	</section>
	<section class="md:p-8 w-4/5 mx-auto flex flex-col items-center">
		<h1 class="mb-8 text-5xl tracking-wider text-[#ffb1b1] underline decoration-wavy">projects</h1>
		<div class="w-full flex flex-col flex-1 gap-16">
			<div class="project">
				<div class="flex md:flex-row flex-col md:justify-between justify-center">
					<div class="flex flex-col">
						<h3 class="md:text-3xl text-2xl md:mb-0 mb-4">Cauldron</h3>
					</div>
					<div class="flex md:flex-row flex-col gap-4">
						<button class="nav-btn md:text-md text-sm">Go To Website</button>
						<button class="md:ml-auto nav-btn md:text-md text-sm">View on GitHub</button>
					</div>
				</div>
				<p class="md:text-xl text-md">
					Cauldron is an open source platform to explore, learn, and save collections of 5e spells.
				</p>
				<div class="flex md:flex-row flex-col justify-between gap-4">
					<img
						class="basis-1/3 md:w-1/3 w-full aspect-square rounded-xl"
						src={alarm}
						alt="spell details"
					/>
					<img
						class="basis-1/3 md:w-1/3 w-full aspect-square rounded-xl"
						src={spellbook}
						alt="spellbook view"
					/>
					<img
						class="basis-1/3 md:w-1/3 w-full aspect-square rounded-xl"
						src={cards}
						alt="spell table"
					/>
				</div>
			</div>
			<div class="project">
				<div class="flex md:flex-row flex-col justify-between">
					<div class="flex flex-col">
						<h3 class="md:text-3xl text-2xl md:mb-0 mb-4">The Paper Earth</h3>
					</div>
					<div class="flex gap-4">
						<button class="nav-btn md:text-md text-sm">Go To Website</button>
						<button class="md:ml-auto nav-btn md:text-md text-sm">View on GitHub</button>
					</div>
				</div>
				<p class="md:text-xl text-md">The Paper Earth is an alt-punk band from Cincinnati, OH!</p>
				<div class="flex md:flex-row flex-col justify-between gap-4">
					<img
						class="basis-2/3 md:w-2/3 w-full aspect-[2/1] rounded-xl"
						src={band}
						alt="band splash page"
					/>
					<img
						class="basis-1/3 md:w-1/3 w-full aspect-square rounded-xl"
						src={photos}
						alt="band photos"
					/>
				</div>
			</div>
		</div>
	</section>
</main>

<style lang="postcss">
	.project {
		width: 100%;
		display: flex;
		flex-direction: column;
		gap: 2rem;
	}

	.nav-btn {
		padding: 8px 12px;
		border-radius: 16px;
		background-color: #ffb1b1;
	}

	@media (max-width: 768px) {
		.nav-btn {
			padding: 4px 8px;
			width: fit-content;
		}
	}
</style>
