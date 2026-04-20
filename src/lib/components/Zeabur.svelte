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
		return `<svg viewBox="0 0 294 229" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid" width="${width}" height="${height}" ${restAttrs}>
  <path fill="#000" d="M114 145h179v84H0v-84h82l114-61H0V0h293v84l-179 61Z" />
  <path fill="#6300FF" d="M195 0H0v84h195V0Z" />
  <path fill="#F40" d="M293 145H115v84h178v-84Z" />
</svg>
`;
	};
</script>

{@html svgContent()}
