<script lang="ts">
	import Badge from '$lib/components/ui/badge/badge.svelte';
	import Button from '$lib/components/ui/button/button.svelte';
	import Card from '$lib/components/ui/card/card.svelte';
	import Mail from '@lucide/svelte/icons/mail';

	/* Assets */
	import logo from '$lib/assets/logo_simple.png';
	import whatsapp from '$lib/assets/svg/whatsapp.svg';
	import instagram from '$lib/assets/svg/instagram.svg';
	import steelpanel_preview from '$lib/assets/img/steelpanel_preview.png';
	import ecommerce_preview from '$lib/assets/img/ecommerce_preview.png';
	import portfolio_preview from '$lib/assets/img/portfolio_preview.png';
	const year = new Date().getFullYear();
</script>

<svelte:head>
	<title>Atrévete.dev | Sitios para Emprendedores</title>
	<meta
		name="description"
		content="Sitios profesionales para Emprendedores con velocidad, soporte y seguridad para negocios en crecimiento."
	/>
</svelte:head>

<div class="min-h-screen bg-[radial-gradient(circle_at_top,rgba(59,130,246,0.16),transparent_45%)]">
	<header class="mx-auto flex max-w-7xl items-center justify-between px-6 py-6 lg:px-8">
		<a href="#top" class="flex items-center gap-3">
			<img src={logo} alt="Atrévete.dev" class="h-10 w-auto object-contain" />
			<span class="text-lg font-semibold tracking-tight">Atrévete.dev</span>
		</a>
		<nav class="hidden items-center gap-6 text-sm text-muted-foreground md:flex">
			<a href="#beneficios" class="transition hover:text-foreground">Beneficios</a>
			<a href="#showcase" class="transition hover:text-foreground">Showcase</a>
			<a href="#planes" class="transition hover:text-foreground">Planes</a>
			<a href="#contacto" class="transition hover:text-foreground">Contacto</a>
		</nav>
	</header>

	<main class="mx-auto flex max-w-7xl flex-col gap-20 px-6 pb-20 lg:px-8">
		<section class="grid items-center gap-10 pt-6 lg:grid-cols-[1.1fr_0.9fr] lg:pt-16">
			<div class="space-y-6">
				<Badge class="border-primary/20 bg-primary/10 text-primary"
					>Sitios para emprendedores, en fácil</Badge
				>
				<h1
					class="max-w-3xl text-4xl font-semibold tracking-tight text-foreground sm:text-5xl lg:text-6xl"
				>
					Tu sitio web profesional, sin dolores de cabeza.
				</h1>
				<p class="max-w-2xl text-lg leading-8 text-muted-foreground">
					Sin costos ocultos, sin configuraciones técnicas y con el soporte que necesitas para que
					tu negocio crezca.
				</p>
				<div class="flex flex-col gap-3 sm:flex-row">
					<a href="#contacto">
						<Button class="w-full cursor-pointer sm:w-auto">Solicitar asesoría</Button>
					</a>
					<a href="#planes">
						<Button variant="outline" class="w-full cursor-pointer sm:w-auto">Ver planes</Button>
					</a>
				</div>
				<div class="flex flex-wrap gap-4 text-sm text-muted-foreground">
					<span>⚡ Velocidad optimizada</span>
					<span>🔒 Seguridad moderna</span>
					<span>☁️ Copias de respaldo</span>
				</div>
			</div>

			<div
				class="rounded-3xl border border-border/80 bg-background/90 p-6 shadow-xl shadow-primary/5 backdrop-blur"
			>
				<div class="space-y-4">
					<div class="flex items-center justify-between">
						<p class="text-sm font-medium text-muted-foreground">Tu plan ideal</p>
					</div>
					<div class="space-y-2">
						<p class="text-4xl font-semibold tracking-tight">Desde $15.000 CLP/mes</p>
						<p class="text-muted-foreground">
							Ideal para emprendedores y profesionales que quieren estabilidad desde el primer día.
						</p>
					</div>
					<div class="grid gap-3 rounded-2xl bg-muted/50 p-4 text-sm text-muted-foreground">
						<div class="flex items-center justify-between">
							<span>Configuración de dominio</span>
							<span class="font-medium text-foreground">Sí</span>
						</div>
						<div class="flex items-center justify-between">
							<span>TLS gratis</span>
							<span class="font-medium text-foreground">Sí</span>
						</div>
						<div class="flex items-center justify-between">
							<span>Soporte técnico</span>
							<span class="font-medium text-foreground">Sí</span>
						</div>
					</div>
				</div>
			</div>
		</section>

		<section id="beneficios" class="grid gap-6 lg:grid-cols-3">
			<Card class="p-6">
				<h2 class="text-xl font-semibold">Seguridad avanzada</h2>
				<p class="mt-3 text-sm leading-7 text-muted-foreground">
					Doble firewall y fail2ban para bloquear bots y ataques. Además, todos los sitios incluyen
					TLS de sitio seguro, hCaptcha y encriptación de discos.
				</p>
			</Card>
			<Card class="p-6">
				<h2 class="text-xl font-semibold">Rendimiento regional</h2>
				<p class="mt-3 text-sm leading-7 text-muted-foreground">
					Servidores en Latinoamérica que reducen la latencia. Cada servidor maneja hasta 40 Gbps de
					tráfico para sitios rápidos y confiables.
				</p>
			</Card>
			<Card class="p-6">
				<h2 class="text-xl font-semibold">Respaldo y capacidad</h2>
				<p class="mt-3 text-sm leading-7 text-muted-foreground">
					Respaldos mensuales automáticos y almacenamiento desde 25 GB, perfecto para fotos, videos
					y archivos descargables sin complicaciones.
				</p>
			</Card>
		</section>

		<section id="showcase" class="space-y-8">
			<div class="max-w-2xl space-y-3">
				<p class="text-sm font-medium tracking-[0.25em] text-primary uppercase">Showcase</p>
				<h2 class="text-3xl font-semibold tracking-tight">
					Trabajos anteriores y plantillas listas
				</h2>
				<p class="text-muted-foreground">
					Selecciona una vista previa de sitio web ya hecha o una plantilla disponible para tu
					negocio.
				</p>
			</div>
			<div class="grid gap-6 md:grid-cols-3">
				<Card class="overflow-hidden p-0">
					<img
						src={portfolio_preview}
						alt="Preview de sitio portfolio"
						class="h-64 w-full object-cover"
					/>
					<div class="p-6">
						<p class="text-sm font-medium tracking-[0.25em] text-primary uppercase">Portfolio</p>
						<h3 class="mt-3 text-xl font-semibold">Sitio para emprendedores</h3>
						<p class="mt-3 text-sm leading-7 text-muted-foreground">
							Vista previa de plantilla para servicios, testimonios y contacto directo con clientes.
						</p>
					</div>
				</Card>
				<Card class="overflow-hidden p-0">
					<img
						src={ecommerce_preview}
						alt="Preview de sitio ecommerce"
						class="h-64 w-full object-cover"
					/>
					<div class="p-6">
						<p class="text-sm font-medium tracking-[0.25em] text-primary uppercase">Ecommerce</p>
						<h3 class="mt-3 text-xl font-semibold">Tienda optimizada</h3>
						<p class="mt-3 text-sm leading-7 text-muted-foreground">
							Preview de plantilla creada para ventas en línea, con atención por WhatsApp y checkout
							listo.
						</p>
					</div>
				</Card>
				<Card class="overflow-hidden p-0">
					<img
						src={steelpanel_preview}
						alt="Preview de sitio profesional"
						class="h-64 w-full object-cover"
					/>
					<div class="p-6">
						<p class="text-sm font-medium tracking-[0.25em] text-primary uppercase">Profesional</p>
						<h3 class="mt-3 text-xl font-semibold">Página de conversión</h3>
						<p class="mt-3 text-sm leading-7 text-muted-foreground">
							Modelo pensado para captar leads, destacar ofertas y facilitar contacto inmediato.
						</p>
					</div>
				</Card>
			</div>
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
					<h3 class="text-xl font-semibold">Portfolio</h3>
					<p class="mt-3 text-sm leading-7 text-muted-foreground">
						Perfecto para sitios personales o proyectos en crecimiento.
					</p>
					<p class="mt-6 text-3xl font-semibold">$15.000 CLP/mes</p>
					<!-- <Button class="mt-6 w-full">Comenzar</Button> -->
				</Card>
				<Card class="relative border-primary/30 p-6 shadow-lg shadow-primary/10">
					<h3 class="flex justify-between text-xl font-semibold">
						Ecommerce
						<Badge class="border-primary/20 bg-primary/10 text-primary">Popular</Badge>
					</h3>
					<p class="mt-3 text-sm leading-7 text-muted-foreground">
						Para emprendedores listos para dar el salto y tener llegar a sus clientes en línea.
					</p>
					<p class="mt-6 text-3xl font-semibold">$25.000 CLP/mes</p>
					<!-- <Button class="mt-6 w-full">Elegir Business</Button> -->
				</Card>
				<Card class="p-6">
					<h3 class="text-xl font-semibold">Profesional</h3>
					<p class="mt-3 text-sm leading-7 text-muted-foreground">
						Para negocios que necesitan estabilidad, velocidad y soporte sólido.
					</p>
					<p class="mt-6 text-3xl font-semibold">$75.000 CLP/mes</p>
					<!-- <Button class="mt-6 w-full">Hablar con ventas</Button> -->
				</Card>
			</div>
			<div
				class="overflow-hidden rounded-3xl border border-border/80 bg-background/90 p-6 shadow-sm"
			>
				<p class="text-sm font-medium text-muted-foreground">Comparativa de planes</p>
				<div class="mt-4 overflow-x-auto">
					<table class="min-w-full border-collapse text-sm">
						<thead>
							<tr
								class="bg-muted/50 text-left text-xs tracking-[0.12em] text-muted-foreground uppercase [&_th]:not-first:text-center"
							>
								<th class="px-4 py-3">Características</th>
								<th class="px-4 py-3">Básico</th>
								<th class="px-4 py-3">Ecommerce</th>
								<th class="px-4 py-3">Profesional</th>
							</tr>
						</thead>
						<tbody class="divide-y divide-border/60 [&_td]:not-first:text-center">
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">Servidor</td>
								<td class="px-4 py-4">Compartido</td>
								<td class="px-4 py-4">Compartido</td>
								<td class="px-4 py-4">Dedicado</td>
							</tr>
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">Costo de configuración</td>
								<td class="px-4 py-4">Incluido</td>
								<td class="px-4 py-4">Incluido</td>
								<td class="px-4 py-4">Incluido</td>
							</tr>
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">CPU</td>
								<td class="px-4 py-4">1</td>
								<td class="px-4 py-4">1</td>
								<td class="px-4 py-4">2</td>
							</tr>
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">RAM</td>
								<td class="px-4 py-4">1 GB</td>
								<td class="px-4 py-4">2 GB</td>
								<td class="px-4 py-4">4 GB</td>
							</tr>
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">Almacenamiento</td>
								<td class="px-4 py-4">25 GB</td>
								<td class="px-4 py-4">50 GB</td>
								<td class="px-4 py-4">80 GB</td>
							</tr>
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">Plantilla profesional</td>
								<td class="px-4 py-4">✅</td>
								<td class="px-4 py-4">✅</td>
								<td class="px-4 py-4">✅</td>
							</tr>
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">Páginas</td>
								<td class="px-4 py-4">Ilimitadas</td>
								<td class="px-4 py-4">Ilimitadas</td>
								<td class="px-4 py-4">Ilimitadas</td>
							</tr>
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">Formulario de contacto</td>
								<td class="px-4 py-4">✅</td>
								<td class="px-4 py-4">✅</td>
								<td class="px-4 py-4">✅</td>
							</tr>
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">Botón de WhatsApp</td>
								<td class="px-4 py-4">✅</td>
								<td class="px-4 py-4">✅</td>
								<td class="px-4 py-4">✅</td>
							</tr>
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">Integración Captcha</td>
								<td class="px-4 py-4">✅</td>
								<td class="px-4 py-4">✅</td>
								<td class="px-4 py-4">✅</td>
							</tr>
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">Respaldos mensuales</td>
								<td class="px-4 py-4">—</td>
								<td class="px-4 py-4">✅</td>
								<td class="px-4 py-4">✅</td>
							</tr>
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">Integración Woocommerce</td>
								<td class="px-4 py-4">—</td>
								<td class="px-4 py-4">✅</td>
								<td class="px-4 py-4">✅</td>
							</tr>
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">Productos</td>
								<td class="px-4 py-4">N/A</td>
								<td class="px-4 py-4">Ilimitados</td>
								<td class="px-4 py-4">Ilimitados</td>
							</tr>
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">Plugin de Webpay</td>
								<td class="px-4 py-4">—</td>
								<td class="px-4 py-4">✅</td>
								<td class="px-4 py-4">✅</td>
							</tr>
							<tr>
								<td class="px-4 py-4 font-medium text-foreground">Soporte dedicado</td>
								<td class="px-4 py-4">—</td>
								<td class="px-4 py-4">—</td>
								<td class="px-4 py-4">✅</td>
							</tr>
						</tbody>
					</table>
				</div>
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
						Nuestro equipo te ayuda a migrar, configurar y mantener tu sitio web sin complicaciones.
					</p>
				</div>
				<a
					href="mailto:contacto@atrevete.dev?subject=Contratar%20plan%20en%20Atr%C3%A9vete.dev"
					aria-label="Contratar por correo electrónico"
					><Button size="lg" class="cursor-pointer">Contratar por <Mail /></Button></a
				>
				<a
					href="https://wa.me/56932638980?text=%C2%A1Hola%21%20Me%20gustar%C3%ADa%20contratar%20uno%20de%20sus%20planes%20en%20Atr%C3%A9vete.dev"
					aria-label="Contratar por WhatsApp"
					><Button size="lg" class="cursor-pointer"
						>Contratar por <img
							src={whatsapp}
							alt="Ícono WhatsApp"
							class="size-1/2 fill-white!"
						/></Button
					></a
				>
			</div>
		</section>
	</main>
</div>

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
				href="https://www.instagram.com/atrevete_dev/"
				target="_blank"
				rel="noopener noreferrer"
				class="flex items-center gap-2 rounded-md bg-background/5 px-3 py-2 transition hover:bg-background/10"
				aria-label="Visitar Instagram"
			>
				<img src={instagram} alt="Instagram logo" class="h-4 w-4" />
				<span class="text-sm">@atrevete_dev</span>
			</a>
		</div>
	</div>
</footer>
