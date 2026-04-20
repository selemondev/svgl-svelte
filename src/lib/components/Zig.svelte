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
		return `<svg viewBox="0 0 300 176" xmlns="http://www.w3.org/2000/svg" fill="none" width="${width}" height="${height}" ${restAttrs}><path fill="#F7A41D" d="M158.395 55.695H85.877V23.453h104.966L262.393 0 142.274 120.337h72.745v32.296H110.048l-71.55 22.655L158.395 55.695ZM0 120.288V23.453h71.746V55.75h-39.46v64.592H80.73l-32.296 32.297H0v-32.351Zm267.709-64.593h-48.45L251.555 23.4H300v129.18h-71.746v-32.296h39.504l-.049-64.588Z"/></svg>`;
	};
</script>

{@html svgContent()}
