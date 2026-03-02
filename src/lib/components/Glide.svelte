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
	const svgContent = `<svg viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="${width}" height="${height}" ${restAttrs}>
 <path d="M0 55L55 0V27C55 42.464 42.464 55 27 55H0Z" fill="#202124">
 </path>
 <path d="M45 73C45 57.536 57.536 45 73 45H100L45 100V73Z" fill="#202124">
 </path>
</svg>`;
</script>

{@html svgContent}
