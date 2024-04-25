<script lang="ts">
	import guitar from '$lib/images/guitar.png';
	import alarm from '$lib/images/alarm.png';
	import spellbook from '$lib/images/spellbook.png';
	import cards from '$lib/images/cards.png';
	import band from '$lib/images/band.png';
	import photos from '$lib/images/photos.png';
</script>

<main class="h-full w-full p-10 flex flex-1">
	<div class="flex flex-col items-center justify-center basis-1/2">
		<p class="text-xl tracking-wider">welcome to</p>
		<h1 class="text-5xl tracking-wider mb-8">ezzy.dog</h1>
		<img class="w-full max-w-4xl" src={guitar} alt="ezzy playing guitar" />
	</div>
	<div class="w-16"></div>
	<div class="flex flex-col items-center basis-1/2">
		<h1 class="text-5xl tracking-wider underline mb-16">my projects</h1>
		<div class="w-full flex-1">
			<div class="project mb-16">
				<div class="flex justify-between mb-2">
					<div class="flex flex-col">
						<h3 class="text-4xl">cauldron</h3>
					</div>
					<div class="flex flex-col gap-4">
						<button class="nav-btn">Go To Website</button>
						<button class="ml-auto w-fit nav-btn">View on GitHub</button>
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
				<p class="text-xl">
					cauldron is an open source platform to explore, learn, and save collections of 5e spells.
				</p>
			</div>
			<div class="project">
				<div class="flex justify-between mb-4">
					<div class="flex flex-col">
						<h3 class="text-4xl">the paper earth</h3>
					</div>
					<div class="flex flex-col gap-4">
						<button class="nav-btn">Go To Website</button>
						<button class="ml-auto w-fit nav-btn">View on GitHub</button>
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
				<p class="text-xl">website for the paper earth, an alt-punk band from cincinnati, OH!</p>
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
</style>
