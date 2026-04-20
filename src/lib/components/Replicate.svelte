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
		return `<svg viewBox="0 0 726 726" fill="#000" xmlns="http://www.w3.org/2000/svg" width="${width}" height="${height}" ${restAttrs}>
<g clip-path="url(#clip0_1_3)">
<path d="M726 310.438V392.476H438.068V726H346.302V310.438H726Z" fill="#000"/>
<path d="M726 155.219V237.402H264.845V726H173.078V155.219H726Z" fill="#000"/>
<path d="M726 0V82.1832H91.7664V726H0V0H726Z" fill="#000"/>
</g>
<defs>
<clipPath id="clip0_1_3">
<rect width="726" height="726" fill="#000"/>
</clipPath>
</defs>
</svg>
`;
	};
</script>

{@html svgContent()}
