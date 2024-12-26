<script lang="ts">
	import church from '../src/church.png';
	import src from '../src/date.svg';
	import type { ChristmasImgProps } from './ImgProps';

	const { onLoad, visible }: ChristmasImgProps = $props();
</script>

<div
	class="relative"
	class:visible
>
	<img
		{src}
		alt=""
	/>
	<img
		src={church}
		class:church
		alt=""
		onload={onLoad}
	/>
</div>

<style lang="scss">
	.church {
		@apply absolute bottom-[6.2%] left-[17.2%] w-[65.6%];
	}
</style>
