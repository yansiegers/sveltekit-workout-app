<script lang="ts">
	import Header from '../../../../components/Header.svelte';

	let exercise = { id: 0, name: 'Shoulder Press' };
	let subHeading = 'Up next: Pec Fly';
</script>

<div class="flex h-screen flex-col">
	<main class=" h-full overflow-y-scroll p-8">
		<Header heading={exercise.name} {subHeading} exit={true} href="/" />

		<a
			class="absolute bottom-2 left-1/2 border-2 border-black bg-white px-5 py-4 text-2xl uppercase"
			style="transform: translate(-50%, -50%);"
			href="?">Next exercise!</a
		>
	</main>
</div>
