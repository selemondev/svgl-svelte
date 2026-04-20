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
		return `<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 48 48" width="${width}" height="${height}" ${restAttrs}><path fill="#453a62" d="M9 43H1l12-18L1 7h8l12 18z"/><path fill="#5e5086" d="M20 7h-8l12 18-12 18h8l8.16-12.24L36 43h8z"/><path fill="#8f4e8b" d="M34.338 24H47v-6H30.338zM40.338 33H47v-6H36.338z"/></svg>`;
	};
</script>

{@html svgContent()}
