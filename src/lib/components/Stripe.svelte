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
		return `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="100 100 312 312" width="${width}" height="${height}" ${restAttrs}><path fill="#533afd" fill-rule="evenodd" d="m120 392 272-57.683V120l-272 58.357z" clip-rule="evenodd"/></svg>`;
	};
</script>

{@html svgContent()}
