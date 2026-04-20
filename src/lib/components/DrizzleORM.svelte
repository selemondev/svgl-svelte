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
		return `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 160 160" width="${width}" height="${height}" ${restAttrs}><rect width="9.631" height="40.852" fill="#121212" rx="4.816" transform="matrix(.87303 .48767 -.49721 .86763 43.48 67.304)"/><rect width="9.631" height="40.852" fill="#121212" rx="4.816" transform="matrix(.87303 .48767 -.49721 .86763 76.94 46.534)"/><rect width="9.631" height="40.852" fill="#121212" rx="4.816" transform="matrix(.87303 .48767 -.49721 .86763 128.424 46.535)"/><rect width="9.631" height="40.852" fill="#121212" rx="4.816" transform="matrix(.87303 .48767 -.49721 .86763 94.957 67.304)"/></svg>`;
	};
</script>

{@html svgContent()}
