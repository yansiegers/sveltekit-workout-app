<script>
	import Header from '../../../components/Header.svelte';
	import WorkoutRoutinePart from '../../../components/WorkoutRoutinePart.svelte';

	let workoutRoutine = { id: 0, name: 'Chest & back' };
	let subHeading = 'Overview Friday 4th of August';

	let exercises = [
		{ sets: 4, reps: 10, name: 'Shoulder Press', weight: 24.1 },
		{ sets: 4, reps: 10, name: 'Pec Fly', weight: 59 },
		{ sets: 4, reps: 10, name: 'Reverse Lat Pull', weight: 41.3 },
		{ sets: 4, reps: 10, name: 'Bench Press', weight: 40 }
	];
</script>

<div class="flex h-screen flex-col">
	<main class="h-full overflow-y-scroll p-8">
		<Header heading={workoutRoutine.name} {subHeading} />

		<div>
			<WorkoutRoutinePart {exercises} />
		</div>
	</main>
</div>
