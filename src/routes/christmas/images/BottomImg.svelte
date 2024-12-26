<script lang="ts">
	import src from '../src/bottom.svg';
	import { type ChristmasImgProps } from './ImgProps';

	const { onLoad, visible }: ChristmasImgProps = $props();
</script>

<div
	class="card relative"
	class:visible
>
	<img
		{src}
		alt=""
		onload={onLoad}
	/>
	<a
		href="https://t.me/+cvT_s8GrLZkxYzgy"
		class="absolute left-[33%] top-[51.8%] h-[8.5%] w-[34%]"
		aria-label="ссылка на наш телеграм-канал"
	></a>
</div>

<style>
	.card {
		margin-top: calc(var(--stock-width) / -5);
	}
</style>
