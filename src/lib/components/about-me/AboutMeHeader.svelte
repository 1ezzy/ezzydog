<script lang="ts">
	import { MediaQuery } from 'svelte/reactivity';
	import { Github, Linkedin, Mail, FileText } from '@lucide/svelte';
	import { intersectionObserverAttachment } from '$lib/utils/attachments';
	import { Icon } from 'svelte-ux';
	import type { Component } from 'svelte';

	const large = new MediaQuery('min-width: 1536px');
	const xlarge = new MediaQuery('min-width: 2560px');

	const links: { href: string; icon: Component; label: string }[] = [
		{
			href: '',
			icon: FileText,
			label: 'Resume (Download)'
		},
		{
			href: 'https://github.com/1ezzy',
			icon: Github,
			label: 'GitHub'
		},
		{
			href: 'mailto:jordanrwm@gmail.com',
			icon: Mail,
			label: 'Email'
		},
		{
			href: 'https://www.linkedin.com/in/jordan-myers-366067184/',
			icon: Linkedin,
			label: 'LinkedIn'
		}
	];

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

{#snippet linkContainer(index: number, icon: Component, label: string)}
	<div
		class="transition duration-400 ease-in-out"
		class:delay-200={index === 0}
		class:delay-300={index === 1}
		class:delay-400={index === 2}
		class:delay-500={index === 3}
		{@attach intersectionObserverAttachment(handleLinkIntersection)}
	>
		<div
			class="flex flex-row items-center gap-4 rounded-full px-4 py-2 hover-fade-in hover:bg-rose-300"
		>
			<Icon data={icon} size={iconSize()} />
			<span class="text-xl">{label}</span>
		</div>
	</div>
{/snippet}

<div class="mb-16 flex flex-row items-center justify-between">
	<h2 id="about" class="pt-16 text-4xl">About Me</h2>
	<div class="flex flex-row items-center gap-4 pt-16">
		{#each links as link, i}
			{#if i === 0}
				<a href={link.href} download>
					{@render linkContainer(i, link.icon, link.label)}
				</a>
			{:else}
				<a href={link.href}>
					{@render linkContainer(i, link.icon, link.label)}
				</a>
			{/if}
			{#if i + 1 < links.length}
				<span
					class="transition duration-400 ease-in-out"
					class:delay-250={i === 0}
					class:delay-350={i === 1}
					class:delay-450={i === 2}
					{@attach intersectionObserverAttachment(handleLinkIntersection)}>|</span
				>
			{/if}
		{/each}
	</div>
</div>
