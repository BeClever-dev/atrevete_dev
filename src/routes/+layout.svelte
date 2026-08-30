<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.ico';
	import logo from '$lib/assets/logo_simple.png';
	import { resolve } from '$app/paths';
	import instagram from '$lib/assets/svg/instagram.svg';
	import whatsapp from '$lib/assets/svg/whatsapp.svg';
	import Mail from '@lucide/svelte/icons/mail';

	let { children } = $props();

	const year = new Date().getFullYear();
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
				<a href={resolve('/#planes')} class="transition hover:text-secondary">Planes</a>
				<a href={resolve('/plantillas')} class="transition hover:text-secondary">Plantillas</a>
				<a href={resolve('/preguntas-frecuentes')} class="transition hover:text-secondary"
					>Preguntas Frecuentes</a
				>
				<a href={resolve('/#contacto')} class="transition hover:text-secondary">Contacto</a>
			</nav>
		</div>
	</header>

	{@render children()}

	<footer class="bg-primary p-8 text-primary-foreground">
		<div
			class="mx-auto flex max-w-7xl flex-col items-center gap-4 px-6 sm:flex-row sm:justify-between"
		>
			<div class="text-center sm:text-left">
				<p class="font-medium">Un servicio de BeClever SpA</p>
				<p class="text-sm text-muted-foreground">© {year} BeClever SpA</p>
			</div>

			<div class="flex flex-wrap items-center gap-3">
				<a
					href="mailto:contacto@atrevete.dev"
					class="flex items-center gap-2 rounded-md bg-background/5 px-3 py-2 transition hover:bg-background/10"
					aria-label="Contactar por correo electrónico"
				>
					<Mail class="h-4 w-4" />
					<span class="text-sm">contacto@atrevete.dev</span>
				</a>

				<a
					href="https://wa.me/56932638980?text=%C2%A1Hola%21%20Me%20gustar%C3%ADa%20cotizar%20uno%20de%20sus%20planes%20en%20Atr%C3%A9vete.dev"
					class="flex items-center gap-2 rounded-md bg-background/5 px-3 py-2 transition hover:bg-background/10"
					aria-label="Contactar por WhatsApp"
				>
					<img src={whatsapp} alt="WhatsApp" class="h-4 w-4" />
					<span class="text-sm">WhatsApp</span>
				</a>

				<a
					href="https://www.instagram.com/atrevete.dev/"
					target="_blank"
					rel="noopener noreferrer"
					class="flex items-center gap-2 rounded-md bg-background/5 px-3 py-2 transition hover:bg-background/10"
					aria-label="Visitar Instagram"
				>
					<img src={instagram} alt="Instagram logo" class="h-4 w-4" />
					<span class="text-sm">@atrevete.dev</span>
				</a>
			</div>
		</div>
	</footer>
</div>
