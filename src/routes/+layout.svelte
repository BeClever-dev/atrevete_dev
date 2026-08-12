<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.ico';

	let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<div class="min-h-screen bg-[radial-gradient(circle_at_top,rgba(59,130,246,0.16),transparent_45%)]">
	{@render children()}
</div>
