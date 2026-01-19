<script lang="ts">
	import './app.css';

	let { children } = $props();
</script>

<div class="flex h-full min-h-screen text-black bg-rose-200">
	{@render children()}
</div>

