<script lang="ts">
	import { T } from '@threlte/core';
	import { Align, Grid, OrbitControls, Text3DGeometry, interactivity } from '@threlte/extras';

	interactivity();
</script>

<T.PerspectiveCamera makeDefault position={[10, 10, 10]}>
	<OrbitControls />
</T.PerspectiveCamera>

<T.DirectionalLight position={[0, 10, 10]} castShadow />

<Align position={[0, 1, 0]}>
	{#snippet children({ align })}
		<T.Mesh castShadow>
			<Text3DGeometry
				text={`Coming soon!`}
				bevelEnabled
				bevelOffset={0}
				bevelSegments={10}
				bevelSize={0.05}
				bevelThickness={0.1}
				curveSegments={12}
				smooth={0.05}
				size={1}
				depth={0.2}
				oncreate={() => {
					align();
				}}
			/>
			<T.MeshStandardMaterial color="#FD3F00" roughness={0.3} metalness={0.7} normalScale={0.5} />
		</T.Mesh>
	{/snippet}
</Align>

<T.AmbientLight intensity={0.3} />

<Grid cellColor="#FE3D00" sectionColor="#FE3D00" />
