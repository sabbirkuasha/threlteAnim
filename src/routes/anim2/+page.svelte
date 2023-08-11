<script>
	import { packB_play } from '../../lib/stores/packB_controller';
	import { Canvas } from '@threlte/core';
	import Scene2 from '../../lib/scene/scene2.svelte';
	import { onMount } from 'svelte';

	function animPlay() {
		$packB_play = 'play';
	}
	function animPause() {
		$packB_play = 'pause';
	}

	onMount(async () => {
		// console.log('called');
		// actionsStore.set('Pause');
	});
</script>

<section class="p-5">
	<div class="canvas-wrapper ring h-[500px]">
		<Canvas>
			<Scene2 />
		</Canvas>
	</div>

	<div class="flex gap-5 py-5 flex-wrap">
		<button on:click={animPlay} class="btn btn-primary">Play</button>
		<button on:click={animPause} class="btn btn-primary">Pause</button>
	</div>
</section>
