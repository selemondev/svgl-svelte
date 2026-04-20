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
		return `<svg viewBox="0 0 256 256" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid" width="${width}" height="${height}" ${restAttrs}><path fill="#F60" d="M128 0A128 128 0 0 0 7 168h38V61l83 83 83-83v107h38A128 128 0 0 0 128 0"/><path fill="#4C4C4C" d="m109 163-36-36v68H19a128 128 0 0 0 218 0h-54v-68l-36 36-19 19-19-19Z"/></svg>`;
	};
</script>

{@html svgContent()}
