<script lang="ts">
	import simfLabel from './src/simf-label.svg';

	const images = $state<
		{ Component: Promise<typeof import('./images/HeadImg.svelte')>; isLoaded?: true }[]
	>([
		{ Component: import('./images/HeadImg.svelte') },
		{ Component: import('./images/DateImg.svelte') },
		{ Component: import('./images/ProgramImg.svelte') },
		{ Component: import('./images/BottomImg.svelte') },
	]);

	const isCanShowImg = (index: number): boolean => {
		for (let i = 0; i <= index; i++) {
			if (!images[i].isLoaded) return false;
		}

		return true;
	};

	$effect(() => {
		console.log(images.map((i) => i.isLoaded));
	});
</script>

<svelte:head>
	<title>С Рождеством Христовым!</title>
	<link
		rel="shortcut icon"
		type="image/ico"
		href={simfLabel}
	/>
</svelte:head>

<div class="card">
	<div class="stock">
		{#each images as img, index (img.Component)}
			{#await img.Component then { default: StockImg }}
				<StockImg
					onLoad={() => (img.isLoaded = true)}
					visible={isCanShowImg(index)}
				/>
			{/await}
		{/each}
	</div>
</div>

<style lang="scss">
	.stock {
		max-width: var(--stock-width);
		margin: auto;
	}

	.card {
		--stock-width: min(600px, 100dvw);
		background-color: #fefaef;
		min-height: 100dvh;
		padding-bottom: calc(var(--stock-width) / 15);

		:global(> *) {
			visibility: hidden;
		}
	}
</style>
