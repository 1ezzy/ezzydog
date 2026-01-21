<script lang="ts">
	import { MediaQuery } from 'svelte/reactivity';
	import { Github, Linkedin, Mail } from '@lucide/svelte';

	import { intersectionObserverAttachment } from '$lib/utils/attachments';

	const large = new MediaQuery('min-width: 1536px');
</script>

<div class="flex min-h-screen w-full flex-col p-16 pt-0 2xl:p-32">
	<div class="mb-16 flex flex-row items-center justify-between">
		<h2 id="projects" class="pt-16 text-4xl">My Projects</h2>
	</div>
	<div class="h-screen"></div>
</div>
