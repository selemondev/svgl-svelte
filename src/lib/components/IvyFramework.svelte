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
		return `<svg viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg" width="${width}" height="${height}" ${restAttrs}>
<path d="M27.0513 0H0.0512695V27.0128C14.9434 27.0128 27.0513 14.9247 27.0513 0Z" fill="#00D18E"/>
</svg>
`;
	};
</script>

{@html svgContent()}
