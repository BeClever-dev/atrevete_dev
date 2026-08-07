<script lang="ts">
	import { cn } from '$lib/utils';

	type ButtonVariant = 'default' | 'outline' | 'secondary' | 'ghost';
	type ButtonSize = 'sm' | 'default' | 'lg';

	let {
		class: className = '',
		variant = 'default' as ButtonVariant,
		size = 'default' as ButtonSize,
		children,
		type = 'button' as 'button' | 'submit' | 'reset',
		...rest
	} = $props();

	const variantClasses: Record<ButtonVariant, string> = {
		default: 'bg-primary text-primary-foreground hover:bg-primary/90',
		outline: 'border border-input bg-background hover:bg-accent hover:text-accent-foreground',
		secondary: 'bg-secondary text-secondary-foreground hover:bg-secondary/80',
		ghost: 'hover:bg-accent hover:text-accent-foreground'
	};

	const sizeClasses: Record<ButtonSize, string> = {
		sm: 'h-9 rounded-md px-3',
		default: 'h-10 rounded-md px-4 py-2',
		lg: 'h-11 rounded-md px-8'
	};
</script>

<button
	{type}
	class={cn(
		'inline-flex items-center justify-center gap-2 text-sm font-medium whitespace-nowrap transition-colors focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 focus-visible:outline-none disabled:pointer-events-none disabled:opacity-50',
		variantClasses[variant],
		sizeClasses[size],
		className
	)}
	{...rest}
>
	{@render children?.()}
</button>
