<script lang="ts">
	/* eslint-disable svelte/no-at-html-tags */

	import {
		Accordion,
		AccordionItem,
		AccordionTrigger,
		AccordionContent
	} from '@/components/ui/accordion';
	import { Separator } from '@/components/ui/separator';

	const faq = {
		Seguridad: {
			'¿Qué es un firewall? ¿Cómo me ayuda tener dos?':
				'<p>Un firewall es un software de control de tráfico con el que bloqueamos tráfico no deseado al servidor y evitamos el uso de puertos no esenciales, protegiéndote de ataques cibernéticos.</p><p>Utilizar dos firewalls en lugar de uno solo es una estrategia de seguridad multicapa donde utilizamos un firewall a nivel de red (antes de que llegue a tu sitio) y otro a nivel del servidor, proveyendo así una protección robusta del servidor.</p>'
		},
		Administración: {
			'¿Qué es una plantilla profesional? ¿Cuáles tienen para elegir?':
				'<p>Las plantillas profesionales que ofrecemos fueron desarrolladas por equipos y profesionales en diseño y desarrollo web, resultando en productos de una calidad excepcional. Puede explorar una lista seleccionada de plantillas disponibles en la sección de plantillas: <a href="https://atrevete.dev/plantillas">https://atrevete.dev/plantillas</a>.</p>',
			'¿Puedo administrar mi sitio?':
				'<p>Nosotros le entregamos a usted un servidor ya configurado con un sitio web desarrollado con WordPress, por lo que no solo puede administrar su propio sitio web, sino que además puede, si lo desea, administrar su servidor.</p>',
			'¿Qué es un plugin?':
				'<p>Los plugins de WordPress son piezas de código escritas por terceros que permiten aumentar o mejorar la funcionalidad de su sitio web. Ejemplos comunes y populares de plugins son Woocommerce, WebPay de Transbank, hCaptcha, entre otros.</p>',
			'¿Qué incluye el soporte dedicado?':
				'<p>Nuestro soporte dedicado incluye la resolución de problemas técnicos, dudas con el manejo del sitio, y apoyo con la administración de su instalación de WordPress a través de un contacto por mensajería instantánea y correo electrónico.</p>'
		},
		Comercial: {
			'¿Cómo puedo comprar un nombre de dominio? ¿Ustedes lo pueden hacer por mí?': `<p>Si desea comprar su propio nombre de dominio, puede hacerlo en cualquier registrador de nombres de dominio. Nosotros le recomendamos utilizar una de las siguientes opciones:<p><ul class="list-disc list-inside space-y-1"><li>Para dominios .cl, <a href="https://www.nic.cl" target="_blank">https://www.nic.cl</a>.</li><li>Para dominios internacionales y otros: <a href="https://www.namecheap.com" target="_blank">https://www.namecheap.com</a>, aunque si lo desea, puede utilizar cualquier otro registrador.</li></ul><br/>
                <p>Nosotros podemos contratar su nombre de dominio .cl por una tarifa anual de $15.000 CLP. El nombre de dominio le será transferido a su cuenta en NIC.cl una vez cancelado su plan de hospedaje web.</p>`,
			'¿Cómo puedo cancelar mi plan?':
				'<p>Puede solicitar la cancelación de su plan en cualquier momento, siempre y cuando no tenga saldos pendientes de pago. Una vez solicitada la cancelación, se le entregará la última copia de seguridad realizada a su sitio web y este se dará de baja. Si deseara retractarse de esta acción, deberá realizar nuevamente la contratación de su servicio y enviarnos su copia de seguridad para poder restaurar su sitio web.</p>',
			'¿Qué información necesito para contratar un plan?': `<p>Dependiendo de si la contratación se hace a nombre de una persona natural (individuo) o jurídica (empresa):</p>
            <ul class="list-disc list-inside space-y-1">
            <li><b>Persona natural:</b> Nombre completo, RUT, número telefónico y un correo electrónico de contacto al que enviar los documentos tributarios e información importante.</li>
            <li><b>Persona jurídica:</b> Nombre completo, RUT, número telefónico y correo electrónico del representante legal además del RUT, giro y razón social de la persona jurídica.</li>
            </ul>`,
			'¿Qué plan es adecuado para mí?': `<p>Dependiendo de sus necesidades, tenemos tres opciones disponibles:</p>
            <ul class="list-disc list-inside space-y-1">
            <li><b>Portfolio:</b> Plan pensado para freelancers, trabajadores independientes, y pequeñas empresas que buscan mostrar su trabajo y tener una mayor visibilidad, entregando confianza a sus clientes.</li>
            <li><b>Ecommerce:</b> Para empresas que buscan vender sus servicios y productos a través de una tienda virtual. Se recomienda tener una empresa formalizada, puesto que algunos portales de pago lo requieren para poder operar con ellos y poder recibir pagos a través de su ecommerce.</li>
            <li><b>Profesional:</b> Plan recomendado para empresas que reciben un mayor tráfico o cuyas operaciones requieren asegurar un funcionamiento de alto desempeño, sin contratiempos y con la confianza de contar con un equipo de soporte técnico dedicado.</li>
            </ul>
            `,
			'¿Puedo cambiarme de plan?':
				'<p>Así es. Puede contactarnos a <a href="mailto:contacto@atrevete.dev">contacto@atrevete.dev</a> para solicitar el cambio de plan sin costo adicional, tanto a uno superior como inferior. Es importante recalcar que el sitio web podría quedar deshabilitado temporalmente mientras dure el cambio, pues en algunos casos significa una migración completa de servidor.</p>',
			'¿Cuál es el ciclo de facturación (aka.: cuándo me cobran)?':
				'<p>El cobro por el servicio de hospedaje se realiza una vez cada 30 días, tomando como fecha de inicio aquella de la contratación misma. En el caso de haber contratado un nombre de dominio a través de nosotros, la facturación de este servicio se realiza una vez al año, utilizando la misma fecha de inicio.</p>',
			'¿Puedo pedir factura?':
				'<p>Sí. En el caso de que cuente con un RUT de persona jurídica, puede solicitar la emisión de facturas en lugar de boletas por el servicio.</p>',
			'¿Qué es BeClever?':
				'<p>BeClever Spa es la compañía detrás del servicio Atrévete.dev. Está formada por profesionales del área informática y de diseño, y se dedica a entregar diversos servicios en el área informática, así como al desarrollo de productos propios. Para más información, puede contactarnos a <a href="mailto:contact@beclever.dev">contact@beclever.dev</a>.</p>'
		}
	};
</script>

<svelte:head>
	<title>Atrévete.dev | Plantillas</title>
	<meta
		name="description"
		content="Plantillas disponibles en Atrévete.dev. Crea tu sitio profesional con velocidad, soporte, seguridad y un diseño de impacto."
	/>
</svelte:head>

<main class="mx-auto flex max-w-7xl flex-col gap-10 px-6 py-20 lg:px-8">
	<section class="space-y-8">
		<div class="max-w-2xl space-y-3">
			<h2 class="text-3xl font-semibold tracking-tight">Preguntas frecuentes</h2>
			<p class="text-muted-foreground">
				Respuestas rápidas a las preguntas más comunes que recibimos. Si lo que busca no está aquí,
				por favor envíenos un correo a
				<a class="underline" href="mailto:contacto@atrevete.dev">contacto@atrevete.dev</a> y estaremos
				felices de responder a todas sus consultas.
			</p>
		</div>
	</section>
	{#each Object.entries(faq) as [section, questions], idx (section)}
		{@const length = Object.keys(faq).length - 1}
		<section class="max-w-2xl space-y-3">
			<h3 class="text-2xl">{section}</h3>
			<Accordion type="single">
				{#each Object.entries(questions) as [question, answer] (question)}
					<AccordionItem value={question}>
						<AccordionTrigger>{question}</AccordionTrigger>
						<AccordionContent>
							{@html answer}
						</AccordionContent>
					</AccordionItem>
				{/each}
			</Accordion>
		</section>
		{#if idx !== length}
			<Separator />
		{/if}
	{/each}
</main>
