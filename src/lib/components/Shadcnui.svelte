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
		return `<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 256 256" width="${width}" height="${height}" ${restAttrs}><path fill="none" d="M0 0h256v256H0z"/><path fill="none" stroke="currentColor" stroke-width="25" stroke-linecap="round" d="M208 128l-80 80M192 40L40 192"/></svg>
`;
	};
</script>

{@html svgContent()}
