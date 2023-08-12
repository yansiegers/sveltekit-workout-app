<script lang="ts">
	import FloatingButton from '../../../../components/FloatingButton.svelte';
	import Header from '../../../../components/Header.svelte';

	let exercise = { id: 0, name: 'Shoulder Press' };
	let subHeading = 'Up next: Pec Fly';
</script>

<div class="flex h-screen flex-col">
	<main class=" h-full overflow-y-scroll p-8">
		<Header heading={exercise.name} {subHeading} exit={true} href="/" />

		<FloatingButton text="Next exercise!" href="?" />
	</main>
</div>
