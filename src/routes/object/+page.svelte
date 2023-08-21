<script>
	import ObjectScene from './../../lib/scene/objectScene.svelte';
	import { Canvas } from '@threlte/core';
</script>

<section class="p-5">
	<div class="canvas-wrapper ring h-screen">
		<Canvas>
			<!-- <Scene2 /> -->
			<ObjectScene />
		</Canvas>
	</div>
</section>
