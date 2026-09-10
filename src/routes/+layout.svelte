<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.ico';
	import logo from '$lib/assets/logo_simple.png';
	import { resolve } from '$app/paths';
	import instagram from '$lib/assets/svg/instagram.svg';
	import whatsapp from '$lib/assets/svg/whatsapp.svg';
	import Mail from '@lucide/svelte/icons/mail';
	import Button from '@/components/ui/button/button.svelte';
	import Menu from '@lucide/svelte/icons/menu';
	import * as Sheet from '$lib/components/ui/sheet/index.js';
	import { ModeWatcher } from 'mode-watcher';
	import MoonIcon from '@lucide/svelte/icons/moon';
	import SunIcon from '@lucide/svelte/icons/sun';
	import { toggleMode } from 'mode-watcher';

	let { children } = $props();

	const links = [
		{ label: 'Beneficios', href: resolve('/#beneficios') },
		{ label: 'Planes', href: resolve('/#planes') },
		{ label: 'Plantillas', href: resolve('/plantillas') },
		{ label: 'Embajadores', href: resolve('/embajadores') },
		{ label: 'Preguntas Frecuentes', href: resolve('/preguntas-frecuentes') },
		{ label: 'Contacto', href: resolve('/#contacto') }
	];

	const year = new Date().getFullYear();
	let open = $state(false);
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<div class="min-h-screen bg-[radial-gradient(circle_at_top,rgba(59,130,246,0.16),transparent_45%)]">
	<header
		class="sticky top-0 z-50 bg-primary px-4 py-4 text-secondary/60 sm:px-6 md:relative lg:px-8"
	>
		<div class="mx-auto flex max-w-7xl items-center justify-between">
			<a href={resolve('/#top')} class="flex items-center gap-3 text-secondary">
				<img src={logo} alt="Atrévete.dev" class="h-10 w-auto object-contain" />
				<span class="hidden text-lg font-semibold tracking-tight md:inline">Atrévete.dev</span>
			</a>
			<nav class="hidden items-center gap-6 text-sm md:flex">
				{#each links as link (link.href)}
					<a href={link.href} class="transition hover:text-secondary">{link.label}</a>
				{/each}
			</nav>

			<!-- Mobile Navigation -->
			<Sheet.Root bind:open>
				<Sheet.Trigger class="md:hidden">
					<Button variant="ghost" size="sm" class="text-secondary">
						<Menu class="size-6" />
						<span class="sr-only">Abrir menú de navegación</span>
					</Button>
				</Sheet.Trigger>
				<Sheet.Content side="right" class="w-72 bg-primary text-secondary">
					<Sheet.Header>
						<Sheet.Title class="text-secondary">Atrévete.dev</Sheet.Title>
						<Sheet.Description class="sr-only">Menú de navegación principal</Sheet.Description>
					</Sheet.Header>
					<nav class="flex flex-col gap-1 px-4 text-base">
						{#each links as link (link.href)}
							<a
								href={link.href}
								onclick={() => (open = false)}
								class="rounded-md px-3 py-3 transition hover:bg-secondary/10 hover:text-secondary"
							>
								{link.label}
							</a>
						{/each}
					</nav>
				</Sheet.Content>
			</Sheet.Root>
		</div>
	</header>

	<ModeWatcher />

	{@render children()}

	<Button
		onclick={toggleMode}
		variant="outline"
		size="icon"
		class="sticky bottom-10 left-10 border-foreground/30 bg-foreground/10 text-foreground hover:cursor-pointer hover:bg-foreground/20 hover:text-foreground dark:border-primary-foreground/40 dark:bg-primary-foreground/10 dark:text-primary-foreground dark:hover:bg-primary-foreground/20 dark:hover:text-primary-foreground"
	>
		<SunIcon
			class="h-[1.2rem] w-[1.2rem] scale-100 rotate-0 transition-all! dark:scale-0 dark:-rotate-90"
		/>
		<MoonIcon
			class="absolute h-[1.2rem] w-[1.2rem] scale-0 rotate-90 transition-all! dark:scale-100 dark:rotate-0"
		/>
		<span class="sr-only">Toggle theme</span>
	</Button>
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
					href="https://wa.me/56920080688?text=%C2%A1Hola%21%20Me%20gustar%C3%ADa%20cotizar%20uno%20de%20sus%20planes%20en%20Atr%C3%A9vete.dev"
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
