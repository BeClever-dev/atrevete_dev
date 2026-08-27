<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.ico';
	import logo from '$lib/assets/logo_simple.png';
	import { resolve } from '$app/paths';

	let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<div class="min-h-screen bg-[radial-gradient(circle_at_top,rgba(59,130,246,0.16),transparent_45%)]">
	<header class="bg-primary px-6 py-6 text-secondary/60 lg:px-8">
		<div class="mx-auto flex max-w-7xl items-center justify-between">
			<a href={resolve('/#top')} class="flex items-center gap-3 text-secondary">
				<img src={logo} alt="Atrévete.dev" class="h-10 w-auto object-contain" />
				<span class="text-lg font-semibold tracking-tight">Atrévete.dev</span>
			</a>
			<nav class="hidden items-center gap-6 text-sm md:flex">
				<a href={resolve('/#beneficios')} class="transition hover:text-secondary">Beneficios</a>
				<a href={resolve('/#plantillas')} class="transition hover:text-secondary">Plantillas</a>
				<a href={resolve('/#planes')} class="transition hover:text-secondary">Planes</a>
				<a href={resolve('/#contacto')} class="transition hover:text-secondary">Contacto</a>
			</nav>
		</div>
	</header>
	{@render children()}
</div>
