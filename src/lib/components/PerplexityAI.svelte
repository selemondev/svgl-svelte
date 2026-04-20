<script lang="ts">
	import type { HTMLAttributes } from 'svelte/elements';

	export interface Props extends HTMLAttributes<SVGElement> {
		width?: number;
		height?: number;
	}

	let { width = 50, height = 50, ...rest }: Props = $props();
	const svgContent = () => {
		const restAttrs = Object.entries(rest)
			.map(([k, v]) => `${k}="${v}"`)
			.join(' ');
		return `<svg 
xmlns="http://www.w3.org/2000/svg" 
viewBox="0 0 48 48" width="${width}" height="${height}" ${restAttrs}>
<path 
fill="none" 
stroke="#20808d" 
stroke-linecap="round" 
stroke-linejoin="round" 
d="M24 4.5v39M13.73 16.573v-9.99L24 16.573m0 14.5L13.73 41.417V27.01L24 16.573m0 0l10.27-9.99v9.99"/>
<path 
fill="none" 
stroke="#20808d" 
stroke-linecap="round" 
stroke-linejoin="round" 
d="M13.73 31.396H9.44V16.573h29.12v14.823h-4.29"/>
<path 
fill="none" 
stroke="#20808d" 
stroke-linecap="round" 
stroke-linejoin="round" 
d="M24 16.573L34.27 27.01v14.407L24 31.073"/>
</svg> `;
	};
</script>

{@html svgContent()}
