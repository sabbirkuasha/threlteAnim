<script>
	import { T } from '@threlte/core';
	import { Environment, OrbitControls, TransformControls, interactivity } from '@threlte/extras';
	import { BoxGeometry, DirectionalLightHelper, MeshStandardMaterial } from 'three';
	import { spring, tweened } from 'svelte/motion';

	import Ship from '../3dModel/Ship.svelte';

	interactivity();

	const scale = spring(1);
	const rotation = spring(0);

	function onEnter() {
		$scale = 1.2;
		$rotation = (15 * Math.PI) / 180;
		// console.log('Enter');
	}
	function onLeave() {
		$scale = 1;
		$rotation = 0;
		// console.log('Leave');
	}
</script>

<Environment path="/hdr/" files="stadium_01_2k.hdr" />

<T.PerspectiveCamera makeDefault position={[0, 0, 10]} lookAt.y={0.0} fov={50}>
	<OrbitControls enableDamping />
</T.PerspectiveCamera>
<T.Group scale={4 * $scale} position={[1, -3, 0]} rotation.y={$rotation}>
	<Ship on:pointerenter={onEnter} on:pointerleave={onLeave} />
</T.Group>
