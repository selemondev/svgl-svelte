<script lang="ts">
	import type { HTMLAttributes } from 'svelte/elements';

	export interface Props extends HTMLAttributes<SVGElement> {
		width?: number;
		height?: number;
	}

	let { width = 50, height = 50, ...rest }: Props = $props();
	const restAttrs = Object.entries(rest)
		.map(([k, v]) => `${k}="${v}"`)
		.join(' ');
	const svgContent = `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 153 152" width="${width}" height="${height}" ${restAttrs}><path fill="#111" fill-rule="evenodd" d="M68.165 68.028C71.979 21.556 33.794-3.367.163.367v32.13c21.897-4.98 41.114 13.83 35.807 35.531zm16.67 0C81.021 21.556 119.206-3.367 152.837.367v32.13c-21.897-4.98-41.113 13.83-35.807 35.531zM60.929 83.972c-3.815 46.472 34.37 71.395 68.002 67.661v-32.13c-21.898 4.98-41.114-13.829-35.807-35.531z" clip-rule="evenodd"/></svg>`;
</script>

{@html svgContent}
