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
		return `<svg viewBox="0 0 1024 1024" xmlns="http://www.w3.org/2000/svg" fill="none" width="${width}" height="${height}" ${restAttrs}><rect width="512" height="256" x="256" y="670.72" fill="#1AD1A5" rx="128"/><circle cx="512" cy="353.28" r="256" fill="#fff"/><circle cx="512" cy="353.28" r="261" stroke="#000" stroke-opacity=".2" stroke-width="10"/><circle cx="512" cy="353.28" r="114.688" fill="#FF9903"/></svg>`;
	};
</script>

{@html svgContent()}
