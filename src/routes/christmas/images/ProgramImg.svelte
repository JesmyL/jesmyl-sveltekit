<script lang="ts">
	import alexey from '../src/alexey.png';
	import src from '../src/program.svg';
	import type { ChristmasImgProps } from './ImgProps';

	const { onLoad, visible }: ChristmasImgProps = $props();
</script>

<div
	class="card relative"
	class:visible
>
	<img
		{src}
		alt=""
	/>
	<img
		src={alexey}
		alt=""
		class="absolute bottom-[5.4%] left-[27.2%] w-[45%]"
		onload={onLoad}
	/>
</div>

<style lang="scss">
	.card {
		margin-top: calc(var(--stock-width) / 10);
	}
</style>
