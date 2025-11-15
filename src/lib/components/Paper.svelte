<script lang="ts">
	import type { HTMLAttributes } from 'svelte/elements';

	export interface Props extends HTMLAttributes<SVGElement> {
		width?: number;
		height?: number;
	}

	let { width = 50, height = 50, ...rest }: Props = $props();
	const restAttrs = Object.entries(rest)
		.map(([k, v]) => `${k}="${v}"`)
		.join(' ');
	const svgContent = `<svg viewBox="0 0 39 39" fill="none" xmlns="http://www.w3.org/2000/svg" width="${width}" height="${height}" ${restAttrs}><path d="M39 24H24V6H6V24H24V39H0V6H6V0H39V24Z" fill="#81ADEC"/></svg>`;
</script>

{@html svgContent}
