<script lang="ts">
	import src from '../src/head.svg';
	import type { ChristmasImgProps } from './ImgProps';

	const { onLoad, visible }: ChristmasImgProps = $props();
</script>

<img
	{src}
	alt=""
	class:visible
	onload={onLoad}
/>
