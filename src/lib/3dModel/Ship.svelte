<!--
Auto-generated by: https://github.com/threlte/threlte/tree/main/packages/gltf
Command: npx @threlte/gltf@1.0.1 ./Ship.glb
-->

<script>
	import { Group } from 'three';
	import { T, forwardEventHandlers } from '@threlte/core';
	import { useGltf } from '@threlte/extras';

	import { Theatre, Studio, Project, Sheet, SheetObject } from '@threlte/theatre';

	export const ref = new Group();

	const gltf = useGltf('/Ship.glb');

	const component = forwardEventHandlers();

	// Using SvelteKit
	import { dev } from '$app/environment';
</script>

<!-- <Studio enabled={dev} />
<Theatre>
	<Sheet name="Sheet A">
		<SheetObject key="ObjectA" let:Transform> -->
<T is={ref} dispose={false} {...$$restProps} bind:this={$component}>
	{#await gltf}
		<slot name="fallback" />
	{:then gltf}
		<T.Mesh
			geometry={gltf.nodes.Cube001.geometry}
			material={gltf.materials.robot}
			position={[0, 0.6, 0]}
			scale={4.67}
		>
			<T.Mesh
				geometry={gltf.nodes.Cylinder.geometry}
				material={gltf.materials.weapon}
				position={[0, 0, -0.08]}
				rotation={[Math.PI / 2, 0, 0]}
			/>
		</T.Mesh>
	{:catch error}
		<slot name="error" {error} />
	{/await}

	<slot {ref} />
</T>
<!-- </SheetObject>
	</Sheet>
</Theatre> -->
