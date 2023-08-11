<script>
	import { actionsStore } from './../../lib/stores/packManage.js';
	import { Canvas } from '@threlte/core';
	import Scene1 from '../../lib/scene1.svelte';
	import { onMount } from 'svelte';

	function animPause() {
		$actionsStore == 'Pause' ? actionsStore.set('Play') : actionsStore.set('Pause');
	}

	onMount(async () => {
		console.log('called');
		// actionsStore.set('Pause');
	});
	$: console.log($actionsStore);
</script>

<section class="p-5">
	<div class="canvas-wrapper ring h-[500px]">
		<Canvas>
			<Scene1 />
		</Canvas>
	</div>

	<button on:click={animPause} class="btn btn-primary w-full">Play/Pause</button>
</section>
