<script>
	import WorkoutRoutinesList from './WorkoutRoutinesList.svelte';
	import Header from '../components/Header.svelte';

	let scheduledWorkoutRoutines = [{ name: 'Chest & back' }];
	let favoriteWorkoutRoutines = [
		{ name: 'Full body' },
		{ name: 'Chest & back' },
		{ name: 'Arms & shoulders' }
	];
</script>

<Header />

<WorkoutRoutinesList title={'Scheduled today'} workoutRoutines={scheduledWorkoutRoutines} />
<WorkoutRoutinesList title={'Favourites'} workoutRoutines={favoriteWorkoutRoutines} />
