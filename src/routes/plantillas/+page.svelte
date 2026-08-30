<script lang="ts">
	import type { Asset } from '$app/types';
	import { resolve } from '$app/paths';
	import Card from '@/components/ui/card/card.svelte';
	import Button from '@/components/ui/button/button.svelte';
	import ExternalLink from '@lucide/svelte/icons/external-link';
	import ArrowLeft from '@lucide/svelte/icons/arrow-left';
	import Badge from '@/components/ui/badge/badge.svelte';

	interface Template {
		img: Asset;
		name: string;
		byName: string;
		byURL: string;
		previewURL: string;
		description: string;
		tags: string[];
	}
	const templates: Template[] = [
		{
			img: '/templates/quantum.png',
			name: 'Quantum',
			byName: 'AncoraThemes',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=AncoraThemes',
			previewURL: 'https://quantum.ancorathemes.com/?storefront=envato-elements',
			description: '',
			tags: ['marketing', 'agencia creativa', 'portfolio']
		},
		{
			img: '/templates/action.png',
			name: 'Action',
			byName: 'ThemeREX',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=ThemeREX',
			previewURL: 'https://action.themerex.net/?storefront=envato-elements',
			description: '',
			tags: ['marketing', 'agencia creativa', 'portfolio']
		},
		{
			img: '/templates/bijoux.png',
			name: 'Bijoux',
			byName: 'vamtam',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=vamtam',
			previewURL: 'https://themes.vamtam.com/?theme=bijoux&storefront=envato-elements',
			description: '',
			tags: ['joyería', 'ecommerce']
		},
		{
			img: '/templates/ergocraft.png',
			name: 'ErgoCraft',
			byName: 'vamtam',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=vamtam',
			previewURL: 'https://ergocraft.vamtam.com/landing-page/?storefront=envato-elements',
			description: '',
			tags: ['muebles', 'ecommerce']
		},
		{
			img: '/templates/darkyn.png',
			name: 'Darkyn',
			byName: 'ThemeGuri',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=ThemeGuri',
			previewURL: 'https://demoxml.com/wp/darkyn/?storefront=envato-elements',
			description: '',
			tags: ['agencia creativa', 'portfolio', 'diseño']
		},
		{
			img: '/templates/literature.png',
			name: 'Literature',
			byName: 'axiomthemes',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=axiomthemes',
			previewURL: 'https://literature.axiomthemes.com/?storefront=envato-elements',
			description: '',
			tags: ['librería', 'cafetería', 'ecommerce']
		},
		{
			img: '/templates/cosma.png',
			name: 'Cosma',
			byName: 'designthemes',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=designthemes',
			previewURL: 'https://cosma.wpengine.com/?storefront=envato-elements',
			description: '',
			tags: ['ecommerce', 'skincare', 'belleza', 'spa']
		},
		{
			img: '/templates/health_supplement.png',
			name: 'Health Supplement',
			byName: 'ThemeGenix',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=ThemeGenix',
			previewURL: 'https://themegenix.net/wp/suxnix-preview/?storefront=envato-elements',
			description: '',
			tags: ['ecommerce', 'salud', 'alimentación', 'fitness']
		},
		{
			img: '/templates/domi.png',
			name: 'Domi',
			byName: 'AncoraThemes',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=AncoraThemes',
			previewURL: 'https://domi.ancorathemes.com/?storefront=envato-elements',
			description: '',
			tags: ['portfolio', 'inmobiliaria', 'arquitectura']
		},
		{
			img: '/templates/craftis.png',
			name: 'Craftis',
			byName: 'ThemeREX',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=ThemeREX',
			previewURL: 'http://craftis.themerex.net/?storefront=envato-elements',
			description: '',
			tags: ['arte', 'ecommerce', 'artesanías', 'hecho a mano']
		},
		{
			img: '/templates/kaffen.png',
			name: 'Kaffen',
			byName: 'bslthemes',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=bslthemes',
			previewURL: 'https://kaffen.bslthemes.com/?storefront=envato-elements',
			description: '',
			tags: ['cafetería', 'ecommerce', 'restaurante', 'bar']
		},
		{
			img: '/templates/aromatica.png',
			name: 'Aromatica',
			byName: 'axiomthemes',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=axiomthemes',
			previewURL: 'https://aromatica.axiomthemes.com/?storefront=envato-elements',
			description: '',
			tags: ['cafetería', 'ecommerce', 'restaurante', 'bar']
		},
		{
			img: '/templates/easyeat.png',
			name: 'EasyEat',
			byName: 'AncoraThemes',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=AncoraThemes',
			previewURL: 'https://easyeat.ancorathemes.com/?storefront=envato-elements',
			description: '',
			tags: ['restaurante', 'bar', 'ecommerce']
		},
		{
			img: '/templates/pubzinne.png',
			name: 'Pubzinne',
			byName: 'axiomthemes',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=axiomthemes',
			previewURL: 'http://pubzinne.axiomthemes.com/?storefront=envato-elements',
			description: '',
			tags: ['restaurante', 'bar', 'reservaciones', 'ecommerce']
		},
		{
			img: '/templates/most.png',
			name: 'Most',
			byName: 'MadSparrow',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=MadSparrow',
			previewURL: 'https://theme.madsparrow.me/most/?storefront=envato-elements',
			description: '',
			tags: ['agencia creativa', 'marketing', 'diseño', 'portfolio']
		},
		{
			img: '/templates/edifice.png',
			name: 'Edifice',
			byName: 'ThemeREX',
			byURL: 'https://app.envato.com/search?itemType=wordpress&filter.portfolio=ThemeREX',
			previewURL: 'https://edifice.themerex.net/?storefront=envato-elements',
			description: '',
			tags: ['construcción', 'profesional', 'ingeniería']
		}
	];
</script>

<svelte:head>
	<title>Atrévete.dev | Plantillas</title>
	<meta
		name="description"
		content="Plantillas disponibles en Atrévete.dev. Crea tu sitio profesional con velocidad, soporte, seguridad y un diseño de impacto."
	/>
</svelte:head>

<main class="mx-auto flex max-w-7xl flex-col gap-20 px-6 py-20 lg:px-8">
	<section class="space-y-8">
		<div class="max-w-2xl space-y-3">
			<h2 class="text-3xl font-semibold tracking-tight">
				Plantillas profesionales y modernas para tu negocio
			</h2>
			<p class="text-muted-foreground">
				Selecciona de nuestra lista curada de plantillas profesionales para tu negocio.
			</p>
		</div>
		<div class="grid gap-6 md:grid-cols-3">
			{#each templates as t (t.img)}
				<Card class="group relative overflow-hidden p-0">
					<img
						src={t.img}
						alt="Previsualización de plantilla {t.name}"
						class="h-64 w-full object-cover"
					/>

					<a
						href={t.previewURL}
						rel="external"
						target="_blank"
						referrerpolicy="no-referrer"
						class="absolute top-2 right-2 md:invisible md:group-hover:visible"
					>
						<Button size="sm" class="cursor-pointer"
							><span class="hidden md:inline">Previsualizar</span>
							<ExternalLink size="12" /></Button
						>
					</a>
					<div class="p-6">
						<a
							href={t.byURL}
							rel="external"
							target="_blank"
							referrerpolicy="no-referrer"
							class="text-sm font-medium text-primary underline"
						>
							By {t.byName}
						</a>
						<h3 class="mt-3 text-xl font-semibold">{t.name}</h3>
						<p class="mt-3 text-sm leading-7 text-muted-foreground">
							{t.description}
						</p>
						<div class="flex flex-wrap gap-2">
							{#each t.tags as tag (tag)}
								<Badge variant="outline">{tag}</Badge>
							{/each}
						</div>
					</div>
				</Card>
			{/each}
		</div>
		<div class="max-w-2xl space-y-3">
			<a href={resolve('/#plantillas')}
				><Button size="lg" class="cursor-pointer"><ArrowLeft /> Volver</Button></a
			>
		</div>
	</section>
</main>
