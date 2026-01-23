<script lang="ts">
	import { MediaQuery } from 'svelte/reactivity';
	import { Github, Linkedin, Mail } from '@lucide/svelte';

	import { intersectionObserverAttachment } from '$lib/utils/attachments';

	const large = new MediaQuery('min-width: 1536px');
	const xlarge = new MediaQuery('min-width: 2560px');
</script>

<div class="flex min-h-screen w-full flex-col p-16 pt-0 3xl:p-32">
	<div class="mb-16 flex flex-row items-center justify-between">
		<h2 id="projects" class="pt-16 text-4xl">My Projects</h2>
	</div>
	<div class="flex h-full items-center justify-center">
		<h2 class="text-4xl">Coming soon...</h2>
	</div>
</div>
