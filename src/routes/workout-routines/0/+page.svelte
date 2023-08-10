<script>
	import Header from '../../../components/Header.svelte';

	let workoutRoutine = { id: 0, name: 'Chest & back' };
	let subHeading = 'Overview Friday 4th of August';
</script>

<div class="flex h-screen flex-col">
	<main class="h-full overflow-y-scroll p-8">
		<Header heading={workoutRoutine.name} {subHeading} />
	</main>
</div>
