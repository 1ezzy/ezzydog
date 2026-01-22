<script lang="ts">
	import { MediaQuery } from 'svelte/reactivity';
	import { Github, Linkedin, Mail } from '@lucide/svelte';
	import { intersectionObserverAttachment } from '$lib/utils/attachments';

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

<div class="mb-16 flex flex-row items-center justify-between">
	<h2 id="about" class="pt-16 text-6xl">About Me</h2>
	<div class="flex flex-row items-center gap-8 pt-16">
		<a
			class="rounded-full p-4 transition ease-in-out hover:bg-rose-300"
			href="https://www.linkedin.com/in/jordan-myers-366067184/"
			{@attach intersectionObserverAttachment(handleLinkIntersection)}
		>
			<div
				class="flex flex-row items-center gap-4 transition delay-200 duration-300 ease-in-out"
				{@attach intersectionObserverAttachment(handleLinkIntersection)}
			>
				<Linkedin size={large ? 32 : 16} />
				<span class="text-xl">LinkedIn</span>
			</div>
		</a>
		<span
			class="transition delay-250 duration-400 ease-in-out"
			{@attach intersectionObserverAttachment(handleLinkIntersection)}>|</span
		>
		<a
			class="rounded-full p-4 transition ease-in-out hover:bg-rose-300"
			href="https://github.com/1ezzy"
			{@attach intersectionObserverAttachment(handleLinkIntersection)}
		>
			<div
				class="flex flex-row items-center gap-4 transition delay-300 duration-300 ease-in-out"
				{@attach intersectionObserverAttachment(handleLinkIntersection)}
			>
				<Github size={large ? 32 : 16} />
				<span class="text-xl">GitHub</span>
			</div>
		</a>
		<span
			class="transition delay-350 duration-400 ease-in-out"
			{@attach intersectionObserverAttachment(handleLinkIntersection)}>|</span
		>
		<a
			class="rounded-full p-4 transition ease-in-out hover:bg-rose-300"
			href="mailto:jordanrwm@gmail.com"
		>
			<div
				class="flex flex-row items-center gap-4 transition delay-400 duration-400 ease-in-out"
				{@attach intersectionObserverAttachment(handleLinkIntersection)}
			>
				<Mail size={large ? 32 : 16} />
				<span class="text-xl">Email</span>
			</div>
		</a>
	</div>
</div>
