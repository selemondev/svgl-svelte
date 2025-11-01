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
	const svgContent = `<svg viewBox="0 0 2500 2500" xmlns="http://www.w3.org/2000/svg" width="${width}" height="${height}" ${restAttrs}><path fill="#c00" d="M0 0h2500v2500H0z"/><path fill="#fff" d="M1241.5 268.5h-973v1962.9h972.9V763.5h495v1467.9h495V268.5z"/></svg>`;
</script>

{@html svgContent}
