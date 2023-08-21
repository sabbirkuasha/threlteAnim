<script>
	import { Canvas } from '@threlte/core';
	import ShipScene from '../../lib/scene/shipScene.svelte';
</script>

<main>
	<h1>Theater Animation</h1>
	<div class=" ring h-[500px]">
		<Canvas>
			<ShipScene />
		</Canvas>
	</div>
</main>
