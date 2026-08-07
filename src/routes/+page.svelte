<script lang="ts">
	import Badge from '$lib/components/ui/badge/badge.svelte';
	import Button from '$lib/components/ui/button/button.svelte';
	import Card from '$lib/components/ui/card/card.svelte';
</script>

<svelte:head>
	<title>Atrévete Hosting | Hosting para WordPress</title>
	<meta
		name="description"
		content="Hosting profesional para WordPress con velocidad, soporte y seguridad para negocios en crecimiento."
	/>
</svelte:head>

<div class="min-h-screen bg-[radial-gradient(circle_at_top,rgba(59,130,246,0.16),transparent_45%)]">
	<header class="mx-auto flex max-w-7xl items-center justify-between px-6 py-6 lg:px-8">
		<div class="text-lg font-semibold tracking-tight">Atrévete Hosting</div>
		<nav class="hidden items-center gap-6 text-sm text-muted-foreground md:flex">
			<a href="#beneficios" class="transition hover:text-foreground">Beneficios</a>
			<a href="#planes" class="transition hover:text-foreground">Planes</a>
			<a href="#contacto" class="transition hover:text-foreground">Contacto</a>
		</nav>
	</header>

	<main class="mx-auto flex max-w-7xl flex-col gap-20 px-6 pb-20 lg:px-8">
		<section class="grid items-center gap-10 pt-6 lg:grid-cols-[1.1fr_0.9fr] lg:pt-16">
			<div class="space-y-6">
				<Badge class="border-primary/20 bg-primary/10 text-primary"
					>Hosting para WordPress sin complicaciones</Badge
				>
				<h1
					class="max-w-3xl text-4xl font-semibold tracking-tight text-foreground sm:text-5xl lg:text-6xl"
				>
					Tu sitio web profesional por menos de lo que cuesta un café al día.
				</h1>
				<p class="max-w-2xl text-lg leading-8 text-muted-foreground">
					Sin costos ocultos, sin configuraciones técnicas y con el soporte que necesitas para que
					tu negocio crezca.
				</p>
				<div class="flex flex-col gap-3 sm:flex-row">
					<Button class="w-full sm:w-auto">Solicitar asesoría</Button>
					<Button variant="outline" class="w-full sm:w-auto">Ver planes</Button>
				</div>
				<div class="flex flex-wrap gap-4 text-sm text-muted-foreground">
					<span>⚡ Velocidad optimizada</span>
					<span>🔒 Seguridad diaria</span>
					<span>☁️ Copias de respaldo</span>
				</div>
			</div>

			<div
				class="rounded-3xl border border-border/80 bg-background/90 p-6 shadow-xl shadow-primary/5 backdrop-blur"
			>
				<div class="space-y-4">
					<div class="flex items-center justify-between">
						<p class="text-sm font-medium text-muted-foreground">Tu plan ideal</p>
						<Badge class="border-emerald-500/20 bg-emerald-500/10 text-emerald-600">Popular</Badge>
					</div>
					<div class="space-y-2">
						<p class="text-4xl font-semibold tracking-tight">Desde $12/mes</p>
						<p class="text-muted-foreground">
							Ideal para tiendas, portafolios y negocios que quieren estabilidad desde el primer
							día.
						</p>
					</div>
					<div class="grid gap-3 rounded-2xl bg-muted/50 p-4 text-sm text-muted-foreground">
						<div class="flex items-center justify-between">
							<span>Dominio incluido</span>
							<span class="font-medium text-foreground">Sí</span>
						</div>
						<div class="flex items-center justify-between">
							<span>SSL gratis</span>
							<span class="font-medium text-foreground">Sí</span>
						</div>
						<div class="flex items-center justify-between">
							<span>Soporte 24/7</span>
							<span class="font-medium text-foreground">Sí</span>
						</div>
					</div>
				</div>
			</div>
		</section>

		<section id="beneficios" class="grid gap-6 lg:grid-cols-3">
			<Card class="p-6">
				<h2 class="text-xl font-semibold">Rendimiento real</h2>
				<p class="mt-3 text-sm leading-7 text-muted-foreground">
					Infraestructura optimizada para WordPress con tiempos de carga rápidos y recursos
					confiables.
				</p>
			</Card>
			<Card class="p-6">
				<h2 class="text-xl font-semibold">Seguridad desde el inicio</h2>
				<p class="mt-3 text-sm leading-7 text-muted-foreground">
					Monitoreo, copias de respaldo automáticas y protección para que tu web siga operativa.
				</p>
			</Card>
			<Card class="p-6">
				<h2 class="text-xl font-semibold">Soporte humano</h2>
				<p class="mt-3 text-sm leading-7 text-muted-foreground">
					No necesitas ser experto. Te acompañamos en cada paso con atención rápida y clara.
				</p>
			</Card>
		</section>

		<section id="planes" class="space-y-6">
			<div class="max-w-2xl space-y-3">
				<p class="text-sm font-medium tracking-[0.25em] text-primary uppercase">Planes flexibles</p>
				<h2 class="text-3xl font-semibold tracking-tight">
					Elige el plan que mejor encaja con tu negocio
				</h2>
			</div>
			<div class="grid gap-6 lg:grid-cols-3">
				<Card class="p-6">
					<h3 class="text-xl font-semibold">Starter</h3>
					<p class="mt-3 text-sm leading-7 text-muted-foreground">
						Perfecto para sitios personales o proyectos en crecimiento.
					</p>
					<p class="mt-6 text-3xl font-semibold">$12/mes</p>
					<Button class="mt-6 w-full">Comenzar</Button>
				</Card>
				<Card class="border-primary/30 p-6 shadow-lg shadow-primary/10">
					<Badge class="border-primary/20 bg-primary/10 text-primary">Más popular</Badge>
					<h3 class="mt-4 text-xl font-semibold">Business</h3>
					<p class="mt-3 text-sm leading-7 text-muted-foreground">
						Para negocios que necesitan estabilidad, velocidad y soporte sólido.
					</p>
					<p class="mt-6 text-3xl font-semibold">$24/mes</p>
					<Button class="mt-6 w-full">Elegir Business</Button>
				</Card>
				<Card class="p-6">
					<h3 class="text-xl font-semibold">Agency</h3>
					<p class="mt-3 text-sm leading-7 text-muted-foreground">
						Ideal para agencias con múltiples sitios y necesidades avanzadas.
					</p>
					<p class="mt-6 text-3xl font-semibold">$49/mes</p>
					<Button class="mt-6 w-full">Hablar con ventas</Button>
				</Card>
			</div>
		</section>

		<section id="contacto" class="rounded-3xl border border-border/80 bg-card p-8 shadow-sm">
			<div class="flex flex-col gap-6 lg:flex-row lg:items-end lg:justify-between">
				<div class="max-w-2xl space-y-3">
					<p class="text-sm font-medium tracking-[0.25em] text-primary uppercase">
						Listo para lanzar
					</p>
					<h2 class="text-3xl font-semibold tracking-tight">
						Haz que tu web sea más rápida, segura y confiable.
					</h2>
					<p class="text-muted-foreground">
						Nuestro equipo te ayuda a migrar, configurar y mantener tu WordPress sin complicaciones.
					</p>
				</div>
				<Button size="lg">Contactar ventas</Button>
			</div>
		</section>
	</main>
</div>
