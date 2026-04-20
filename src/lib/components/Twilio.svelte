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
		return `<svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg" width="${width}" height="${height}" ${restAttrs}><g transform="translate(0 .047) scale(.93704)" fill="#e31e26"><path d="M34.1 0C15.3 0 0 15.3 0 34.1s15.3 34.1 34.1 34.1C53 68.3 68.3 53 68.3 34.1S53 0 34.1 0zm0 59.3C20.3 59.3 9 48 9 34.1 9 20.3 20.3 9 34.1 9 48 9 59.3 20.3 59.3 34.1 59.3 48 48 59.3 34.1 59.3z"/><circle cx="42.6" cy="25.6" r="7.1"/><circle cx="42.6" cy="42.6" r="7.1"/><circle cx="25.6" cy="42.6" r="7.1"/><circle cx="25.6" cy="25.6" r="7.1"/></g></svg>`;
	};
</script>

{@html svgContent()}
