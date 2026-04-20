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
		return `<svg xmlns="http://www.w3.org/2000/svg" id="Logos" viewBox="0 0 50 72" width="${width}" height="${height}" ${restAttrs}><defs><style>.cls-1{fill:#a067da;fill-rule:evenodd;stroke-width:0}</style></defs><path d="m17.2 17.5 15.5 9v18l-15.5-9v-18ZM34.5 26.5v18l15.5-9v-18l-15.5 9ZM0 7.5v18l15.5 9v-18L0 7.5ZM17.2 55.5l15.5 9v-18l-15.5-9v18Z" class="cls-1"/></svg>`;
	};
</script>

{@html svgContent()}
