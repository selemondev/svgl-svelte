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
		return `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 600 600" width="${width}" height="${height}" ${restAttrs}><path fill="#DCFF50" fill-rule="evenodd" d="M150 150h299.832v300H150V150Zm269.168 30.682v238.636H180.665V180.682h238.503Z" clip-rule="evenodd"/></svg>`;
	};
</script>

{@html svgContent()}
