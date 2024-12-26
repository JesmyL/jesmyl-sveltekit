<script lang="ts">
	import { goto } from '$app/navigation';
	import { onMount } from 'svelte';

	onMount(() => {
		if (window.location.hash === '#/christmas' || window.location.hash === '#christmas')
			setTimeout(goto, 100, 'christmas');
	});
</script>
