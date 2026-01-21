<script lang="ts">
	import { MediaQuery } from 'svelte/reactivity';
	import { ArrowBigDown, Github, Linkedin, Mail } from '@lucide/svelte';
	import { intersectionObserverAttachment } from '$lib/utils/attachments';

	import flower2 from '$lib/assets/flower2.png';

	const large = new MediaQuery('min-width: 1536px');

	const handleLinkIntersection = (entry: IntersectionObserverEntry) => {
		if (entry.isIntersecting) {
			entry.target.classList.add('opacity-100');
			entry.target.classList.remove('opacity-0');
		} else {
			entry.target.classList.add('opacity-0');
			entry.target.classList.remove('opacity-100');
		}
	};
</script>

<div class="flex min-h-screen w-full flex-col p-16 pt-0 2xl:p-32">
	<div class="mb-16 flex flex-row items-center justify-between">
		<h2 id="about" class="pt-16 text-6xl">About Me</h2>
		<div class="flex flex-row items-center gap-8 pt-16">
			<a
				class="flex flex-row items-center gap-4 rounded-full p-4 transition delay-200 duration-400 ease-in-out hover:bg-rose-300"
				href="https://www.linkedin.com/in/jordan-myers-366067184/"
				{@attach intersectionObserverAttachment(handleLinkIntersection)}
			>
				<Linkedin size={large ? 32 : 16} />
				<span class="text-xl">LinkedIn</span>
			</a>
			<span
				class="transition delay-250 duration-400 ease-in-out"
				{@attach intersectionObserverAttachment(handleLinkIntersection)}>|</span
			>
			<a
				class="flex flex-row items-center gap-4 rounded-full p-4 transition delay-300 duration-400 ease-in-out hover:bg-rose-300"
				href="https://github.com/1ezzy"
				{@attach intersectionObserverAttachment(handleLinkIntersection)}
			>
				<Github size={large ? 32 : 16} />
				<span class="text-xl">GitHub</span>
			</a>
			<span
				class="transition delay-350 duration-400 ease-in-out"
				{@attach intersectionObserverAttachment(handleLinkIntersection)}>|</span
			>
			<a
				class="flex flex-row items-center gap-4 rounded-full p-4 transition delay-400 duration-400 ease-in-out hover:bg-rose-300"
				href="mailto:jordanrwm@gmail.com"
				{@attach intersectionObserverAttachment(handleLinkIntersection)}
			>
				<Mail size={large ? 32 : 16} />
				<span class="text-xl">Email</span>
			</a>
		</div>
	</div>
	<div
		class="relative my-auto flex max-h-400 w-full flex-1 flex-row items-center justify-center overflow-hidden py-8"
	>
		<div class="absolute left-0 h-4/5 w-full rounded-full bg-violet-400"></div>
		<div
			class="absolute left-0 flex aspect-square h-9/10 flex-col items-center justify-center gap-8 rounded-full border-2 border-white bg-violet-300 px-24 2xl:gap-16 2xl:border-4 2xl:px-64"
		>
			<span class="font-cal text-md">
				I'm a front-end developer with a passion for building intuitive, robust interfaces and
				tackling any technical challenges I can. I love taking on new projects as a way to learn and
				enjoy exploring new ideas by writing code!
			</span>
			<span class="font-cal text-md">
				Check out my resume and some of my favorite technologies to the right along with some of the
				projects I have developed below!</span
			>
			<a href="#projects" aria-label="Scroll to Projects" class="text-violet-400">
				<ArrowBigDown size={large ? 48 : 24} />
			</a>
			<img
				src={flower2}
				alt="separating flower"
				class="absolute top-1/2 -right-32 z-10 w-32 -translate-x-1/2 -translate-y-1/2"
			/>
		</div>
	</div>
</div>
