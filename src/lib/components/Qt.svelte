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
		return `<svg
    xmlns="http://www.w3.org/2000/svg"
    viewBox="0 0 54 43"
     width="${width}" height="${height}" ${restAttrs}><path fill="#0c0" d="M1 42V10l9-9h43v33l-9 9z"></path><text
        x="9"
        y="32"
        fill="#FFF"
        font-family="Arial"
        font-size="32">Qt</text
    ></svg
>
`;
	};
</script>

{@html svgContent()}
