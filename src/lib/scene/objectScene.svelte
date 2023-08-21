<script>
	import { T } from '@threlte/core';
	import {
		Environment,
		OrbitControls,
		TransformControls,
		interactivity,
		ContactShadows,
		SoftShadows,
		HTML
	} from '@threlte/extras';
	import { BoxGeometry, DirectionalLightHelper, MeshStandardMaterial } from 'three';
	import { spring, tweened } from 'svelte/motion';
	import Ship from '../3dModel/Ship.svelte';
</script>

<Environment path="/hdr/" files="stadium_01_2k.hdr" isBackground={false} />

<T.PerspectiveCamera makeDefault position={[3, 3, 10]} lookAt.y={0.0} fov={30}>
	<OrbitControls enableDamping />
</T.PerspectiveCamera>

<!-- <T.GridHelper args={[10, 10]} /> -->

<!-- <T.Mesh position={[0, 0.5, 0]} scale={7}>
	<T.SphereGeometry />
	<T.MeshStandardMaterial roughness={0} color="gray" side={1} />
</T.Mesh> -->

<TransformControls>
	<Ship scale={2} position={[0, -1, 0]} />
</TransformControls>
<HTML position.y={2} scale={0.5} transform occlude={false} sprite={false} center>
	<button class="btn btn-primary"> This is a ship </button>
</HTML>

<!-- <SoftShadows focus={10} size={10} samples={10} /> -->
<ContactShadows scale={20} blur={2} far={2.5} opacity={1} position={[0, -1, 0]} />
