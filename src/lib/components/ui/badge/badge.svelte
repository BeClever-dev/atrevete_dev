<script lang="ts">
	import { cn } from '$lib/utils';

	let { class: className = '', children, ...rest } = $props();
</script>

<span
	class={cn(
		'inline-flex items-center rounded-full border px-2.5 py-0.5 text-xs font-semibold',
		className
	)}
	{...rest}
>
	{@render children?.()}
</span>
