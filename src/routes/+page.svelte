<script lang="ts">
	import guitar from '$lib/images/guitar.png';
	import alarm from '$lib/images/alarm.png';
	import spellbook from '$lib/images/spellbook.png';
	import cards from '$lib/images/cards.png';
	import band from '$lib/images/band.png';
	import photos from '$lib/images/photos.png';
</script>

<main class="h-full w-full p-10 flex md:flex-row flex-col flex-1">
	<div class="p-4 flex flex-col items-center justify-center basis-1/2">
		<p class="text-xl tracking-wider">welcome to</p>
		<h1 class="text-5xl tracking-wider mb-8">ezzy.dog</h1>
		<img
			class="w-full lg:max-w-lg max-w-4xl aspect-square"
			src={guitar}
			alt="ezzy playing guitar"
		/>
	</div>
	<div class="md:w-16"></div>
	<div class="p-4 flex flex-col items-center basis-1/2 md:overflow-y-auto">
		<h1 class="lg:text-4xl text-5xl tracking-wider underline mb-16">my projects</h1>
		<div class="w-full flex-1">
			<div class="project mb-16">
				<div class="flex md:flex-row flex-col md:justify-between justify-center mb-8">
					<div class="flex flex-col">
						<h3 class="md:text-3xl text-2xl md:mb-0 mb-4">cauldron</h3>
					</div>
					<div class="flex gap-4">
						<button class="nav-btn md:text-md text-sm">Go To Website</button>
						<button class="md:ml-auto nav-btn md:text-md text-sm">View on GitHub</button>
					</div>
				</div>
				<div class="flex justify-between mb-4">
					<img
						class="m-2 basis-1/3 w-1/3 aspect-square rounded-xl"
						src={alarm}
						alt="spell details"
					/>
					<img
						class="m-2 basis-1/3 w-1/3 aspect-square rounded-xl"
						src={spellbook}
						alt="spellbook view"
					/>
					<img class="m-2 basis-1/3 w-1/3 aspect-square rounded-xl" src={cards} alt="spell table" />
				</div>
				<p class="md:text-xl text-md">
					cauldron is an open source platform to explore, learn, and save collections of 5e spells.
				</p>
			</div>
			<div class="project">
				<div class="flex md:flex-row flex-col justify-between mb-8">
					<div class="flex flex-col">
						<h3 class="md:text-3xl text-2xl md:mb-0 mb-4">the paper earth</h3>
					</div>
					<div class="flex gap-4">
						<button class="nav-btn md:text-md text-sm">Go To Website</button>
						<button class="md:ml-auto nav-btn md:text-md text-sm">View on GitHub</button>
					</div>
				</div>
				<div class="flex justify-between mb-4">
					<img
						class="ml-2 mr-4 basis-2/3 w-2/3 aspect-[2/1] rounded-xl"
						src={band}
						alt="band splash page"
					/>
					<img
						class="mr-2 basis-1/3 w-1/3 aspect-square rounded-xl"
						src={photos}
						alt="band photos"
					/>
				</div>
				<p class="md:text-xl text-md">
					website for the paper earth, an alt-punk band from cincinnati, OH!
				</p>
			</div>
		</div>
	</div>
</main>

<style lang="postcss">
	.project {
		width: 100%;
		max-width: 1024px;
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
