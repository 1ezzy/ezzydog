<script lang="ts">
	import { MediaQuery } from 'svelte/reactivity';
	import { Github, Linkedin, Mail } from '@lucide/svelte';
	import { intersectionObserverAttachment } from '$lib/utils/attachments';

	const large = new MediaQuery('min-width: 1536px');
	const xlarge = new MediaQuery('min-width: 2560px');

	const iconSize = $derived(() => (xlarge.current ? 32 : large.current ? 24 : 16));

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
	<h2 id="about" class="pt-16 text-4xl">About Me</h2>
	<div class="flex flex-row items-center gap-8 pt-16">
		<a href="https://www.linkedin.com/in/jordan-myers-366067184/">
			<div
				class="transition delay-200 duration-300 ease-in-out"
				{@attach intersectionObserverAttachment(handleLinkIntersection)}
			>
				<div
					class="flex flex-row items-center gap-4 rounded-full px-4 py-2 hover-fade-in hover:bg-rose-300"
				>
					<Linkedin size={iconSize()} />
					<span class="text-xl">LinkedIn</span>
				</div>
			</div>
		</a>
		<span
			class="transition delay-250 duration-400 ease-in-out"
			{@attach intersectionObserverAttachment(handleLinkIntersection)}>|</span
		>
		<a href="https://github.com/1ezzy">
			<div
				class="transition delay-300 duration-300 ease-in-out"
				{@attach intersectionObserverAttachment(handleLinkIntersection)}
			>
				<div
					class="flex flex-row items-center gap-4 rounded-full px-4 py-2 hover-fade-in hover:bg-rose-300"
				>
					<Github size={iconSize()} />
					<span class="text-xl">GitHub</span>
				</div>
			</div>
		</a>
		<span
			class="transition delay-350 duration-400 ease-in-out"
			{@attach intersectionObserverAttachment(handleLinkIntersection)}>|</span
		>
		<a href="mailto:jordanrwm@gmail.com">
			<div
				class="transition delay-400 duration-300 ease-in-out"
				{@attach intersectionObserverAttachment(handleLinkIntersection)}
			>
				<div
					class="flex flex-row items-center gap-4 rounded-full px-4 py-2 hover-fade-in hover:bg-rose-300"
				>
					<Mail size={iconSize()} />
					<span class="text-xl">Email</span>
				</div>
			</div>
		</a>
	</div>
</div>
