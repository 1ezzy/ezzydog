<script lang="ts">
	import './app.css';

	let { children } = $props();
</script>

<div class="flex h-full min-h-screen justify-center bg-rose-200 text-black">
	{@render children()}
</div>
