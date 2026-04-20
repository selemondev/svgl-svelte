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
		return `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 80 60" width="${width}" height="${height}" ${restAttrs}><path fill="#171717" d="M0 28.5h3.019v3H0zM10.566 15h6.038v6h-6.038zm0 24h6.038v6h-6.038zM20.629 1h10.063v10H20.629zm2.013 26h6.037v6h-6.037zm-2.013 22h10.063v10H20.629zm12.075-36h10.063v10H32.704zm0 24h10.063v10H32.704zm11.07-37h12.075v12H43.774zm1.006 25h10.063v10H44.78zm-1.006 23h12.075v12H43.774zM55.85 12h12.074v12H55.85zm0 24h12.074v12H55.85zm12.075-12H80v12H67.924z"/></svg>`;
	};
</script>

{@html svgContent()}
