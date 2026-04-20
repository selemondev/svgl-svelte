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
		return `
<svg viewBox="0 0 512 512" fill="none" xmlns="http://www.w3.org/2000/svg" width="${width}" height="${height}" ${restAttrs}>
<rect width="512" height="512" fill="#FDFCFC"/>
<path d="M320 224V352H192V224H320Z" fill="#E6E5E6"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M384 416H128V96H384V416ZM320 160H192V352H320V160Z" fill="#17181C"/>
</svg>`;
	};
</script>

{@html svgContent()}
