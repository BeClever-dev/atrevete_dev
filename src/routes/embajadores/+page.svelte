<script lang="ts">
	import Badge from '$lib/components/ui/badge/badge.svelte';
	import Button from '$lib/components/ui/button/button.svelte';
	import Card from '$lib/components/ui/card/card.svelte';
	import Gift from '@lucide/svelte/icons/gift';
	import Percent from '@lucide/svelte/icons/percent';
	import ReceiptText from '@lucide/svelte/icons/receipt-text';
	import Users from '@lucide/svelte/icons/users';
	import Mail from '@lucide/svelte/icons/mail';
	import whatsapp from '$lib/assets/svg/whatsapp.svg';

	const plans: Array<{ label: string; value: number }> = [
		{ label: 'Portfolio', value: 15000 },
		{ label: 'Ecommerce', value: 25000 },
		{ label: 'Profesional', value: 35000 }
	];

	const commissionRate = 0.1;
	let selectedPlan = $state<number>(plans[1].value);
	let clients = $state(5);

	let monthlyCommission = $derived(selectedPlan * clients * commissionRate);

	const moneyFormatter = new Intl.NumberFormat('es-CL', {
		style: 'currency',
		currency: 'CLP',
		maximumFractionDigits: 0
	});
</script>

<svelte:head>
	<title>Atrévete.dev | Embajadores</title>
	<meta
		name="description"
		content="Programa de embajadores de Atrévete.dev: comparte tu código, gana comisión por publicidad y ayuda a más clientes a acceder a un descuento del 10% en sus primeros 6 meses."
	/>
</svelte:head>

<main class="mx-auto flex max-w-7xl flex-col gap-16 px-6 py-20 lg:px-8">
	<section class="grid items-center gap-10 lg:grid-cols-[1.05fr_0.95fr]">
		<div class="space-y-6">
			<Badge class="border-primary/20 bg-primary/10 text-primary">Programa de embajadores</Badge>
			<h1 class="max-w-3xl text-4xl font-semibold tracking-tight text-foreground sm:text-5xl">
				Recomienda Atrévete.dev y gana comisiones por publicidad.
			</h1>
			<p class="max-w-2xl text-lg leading-8 text-muted-foreground">
				Un embajador es un promotor o afiliado de Atrévete.dev. Su labor es la difusión y
				recomendación del servicio, siempre dejando claro que la venta se celebra directamente entre
				Atrévete.dev y el cliente. El embajador no intermedia ni celebra la venta, sino que
				recomienda el servicio y comparte un código asociado.
			</p>
		</div>

		<div
			class="rounded-3xl border border-border/80 bg-background/90 p-6 shadow-xl shadow-primary/5"
		>
			<div class="space-y-5">
				<div class="flex items-center justify-between">
					<p class="text-sm font-medium text-muted-foreground">Beneficio para tus clientes</p>
					<Gift class="h-5 w-5 text-primary" />
				</div>
				<div class="space-y-2">
					<p class="text-4xl font-semibold tracking-tight">10% off</p>
					<p class="text-muted-foreground">
						Tus clientes pueden usar su código para reclamar un descuento del 10% en los primeros 6
						meses de suscripción.
					</p>
				</div>
			</div>
		</div>
	</section>

	<section id="como-funciona" class="space-y-8">
		<div class="max-w-2xl space-y-3">
			<p class="text-sm font-medium tracking-[0.22em] text-primary uppercase">Cómo funciona</p>
			<h2 class="text-3xl font-semibold tracking-tight">Una estructura simple y clara</h2>
		</div>
		<div class="grid gap-6 md:grid-cols-2 xl:grid-cols-4">
			<Card class="p-6">
				<div
					class="mb-4 flex h-12 w-12 items-center justify-center rounded-xl bg-primary/10 text-primary"
				>
					<Users class="h-5 w-5" />
				</div>
				<h3 class="text-xl font-semibold">1. Te registras</h3>
				<p class="mt-3 text-sm leading-7 text-muted-foreground">
					Recibes un código exclusivo como embajador de Atrévete.dev para compartir con tus
					clientes.
				</p>
			</Card>
			<Card class="p-6">
				<div
					class="mb-4 flex h-12 w-12 items-center justify-center rounded-xl bg-primary/10 text-primary"
				>
					<Gift class="h-5 w-5" />
				</div>
				<h3 class="text-xl font-semibold">2. Tu cliente ahorra</h3>
				<p class="mt-3 text-sm leading-7 text-muted-foreground">
					Cada cliente que use el código obtiene un 10% de descuento en sus primeros 6 meses de
					contratación.
				</p>
			</Card>
			<Card class="p-6">
				<div
					class="mb-4 flex h-12 w-12 items-center justify-center rounded-xl bg-primary/10 text-primary"
				>
					<Percent class="h-5 w-5" />
				</div>
				<h3 class="text-xl font-semibold">3. Ganas comisión</h3>
				<p class="mt-3 text-sm leading-7 text-muted-foreground">
					Por las compras asociadas a tu código, recibes una comisión por servicios de publicidad
					equivalente al 10% del monto asociado a la compra del cliente.
				</p>
			</Card>
			<Card class="p-6">
				<div
					class="mb-4 flex h-12 w-12 items-center justify-center rounded-xl bg-primary/10 text-primary"
				>
					<ReceiptText class="h-5 w-5" />
				</div>
				<h3 class="text-xl font-semibold">4. Cobro mensual</h3>
				<p class="mt-3 text-sm leading-7 text-muted-foreground">
					Cada mes generamos un resumen mensual de comisiones con tus ganancias y tú debes emitir
					una boleta de honorarios para que podamos transferir el pago.
				</p>
			</Card>
		</div>
	</section>

	<section class="rounded-3xl border border-border/80 bg-background/90 p-8 shadow-sm">
		<div class="max-w-3xl space-y-4">
			<p class="text-sm font-medium tracking-[0.22em] text-primary uppercase">
				Reglas del programa
			</p>
			<h2 class="text-3xl font-semibold tracking-tight">Lo importante para entender el programa</h2>
			<ul class="space-y-3 text-base leading-7 text-muted-foreground">
				<li>• Un embajador es un promotor o afiliado de Atrévete.dev.</li>
				<li>
					• Su labor es la difusión y recomendación del servicio, dejando siempre claro que la venta
					se celebra directamente entre Atrévete.dev y el cliente.
				</li>
				<li>
					• Cada embajador recibe un código que puede ser usado por sus clientes para reclamar un
					10% de descuento en los primeros 6 meses de su suscripción.
				</li>
				<li>
					• La comisión por servicios de publicidad corresponde al 10% del monto asociado a las
					compras vinculadas al código del embajador.
				</li>
				<li>
					• Todo afiliado que recomiende el servicio a cambio de dinero debe indicarlo visiblemente:
					“Afiliado de Atrévete.dev” o “Gano comisión por servicios de publicidad”.
				</li>
				<li>
					• Sólo se aceptan embajadores residentes en Chile, con RUT chileno vigente, que puedan
					emitir boletas de honorarios dentro del país.
				</li>
				<li>
					• Mensualmente se genera un resumen mensual de comisiones con el monto de la comisión a
					pagar y el embajador debe emitir una boleta de honorarios para que podamos transferir el
					pago.
				</li>
			</ul>
		</div>
	</section>

	<section class="rounded-3xl border border-border/80 bg-card p-8 shadow-sm">
		<div class="grid gap-8 lg:grid-cols-[1.1fr_0.9fr] lg:items-center">
			<div class="space-y-6">
				<div class="space-y-3">
					<p class="text-sm font-medium tracking-[0.22em] text-primary uppercase">
						Calcula tus ganancias
					</p>
					<h2 class="text-3xl font-semibold tracking-tight">Tu comisión estimada</h2>
				</div>

				<div class="space-y-4">
					<p class="text-sm font-medium text-muted-foreground">Selecciona el plan promedio</p>
					<div class="grid gap-3 sm:grid-cols-3">
						{#each plans as plan (plan.label)}
							<button
								type="button"
								class={`cursor-pointer rounded-2xl border px-4 py-3 text-left transition ${
									selectedPlan === plan.value
										? 'border-primary bg-primary text-primary-foreground shadow-sm'
										: 'border-border bg-background text-foreground hover:border-primary/50'
								}`}
								onclick={() => (selectedPlan = plan.value)}
							>
								<p class="text-sm font-medium">{plan.label}</p>
								<p class="mt-1 text-lg font-semibold">{moneyFormatter.format(plan.value)}</p>
							</button>
						{/each}
					</div>
				</div>

				<div class="space-y-4">
					<div class="flex items-center justify-between gap-4">
						<label for="clients" class="text-sm font-medium text-muted-foreground">
							Clientes activos
						</label>
						<span class="rounded-full bg-primary/10 px-2.5 py-1 text-sm font-semibold text-primary">
							{clients}
						</span>
					</div>
					<input
						id="clients"
						type="range"
						min="1"
						max="30"
						bind:value={clients}
						class="w-full accent-primary"
					/>
				</div>
			</div>

			<div class="rounded-3xl border border-primary/20 bg-primary/5 p-6 shadow-inner">
				<div class="space-y-5">
					<p class="text-sm font-medium tracking-[0.2em] text-primary uppercase">
						Comisión estimada
					</p>
					<div>
						<p class="text-4xl font-semibold tracking-tight sm:text-5xl">
							{moneyFormatter.format(monthlyCommission)}
						</p>
					</div>
					<div class="grid gap-3 rounded-2xl bg-background/80 p-4 text-sm text-muted-foreground">
						<div class="flex items-center justify-between gap-4">
							<span>Fórmula</span>
							<span class="font-medium text-foreground">
								{moneyFormatter.format(selectedPlan)} × {clients} × 10%
							</span>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<section class="rounded-3xl border border-border/80 bg-card p-8 shadow-sm">
		<div class="flex flex-col gap-6 lg:flex-row lg:items-end lg:justify-between">
			<div class="max-w-2xl space-y-3">
				<p class="text-sm font-medium tracking-[0.22em] text-primary uppercase">
					¿Listo para empezar?
				</p>
				<h2 class="text-3xl font-semibold tracking-tight">
					Recomienda y gana con cada cliente que use tu código.
				</h2>
			</div>

			<a
				href="mailto:contacto@atrevete.dev?subject=Quiero%20ser%20embajador%20de%20Atr%C3%A9vete.dev"
				aria-label="Hablar por correo electrónico"
			>
				<Button size="lg" class="cursor-pointer">Hablar por <Mail /></Button>
			</a>
			<a
				href="https://wa.me/56932638980?text=%C2%A1Hola%21%20Quiero%20saber%20m%C3%A1s%20sobre%20el%20programa%20de%20embajadores%20de%20Atr%C3%A9vete.dev"
				aria-label="Hablar por WhatsApp"
			>
				<Button size="lg" class="cursor-pointer"
					>Hablar por <img
						src={whatsapp}
						alt="Ícono WhatsApp"
						class="size-1/2 fill-white!"
					/></Button
				>
			</a>
		</div>
	</section>
</main>
