<script>
	import WorkoutRoutinesList from './WorkoutRoutinesList.svelte';
	import Header from '../components/Header.svelte';

	let scheduledWorkoutRoutines = [{ id: 0, name: 'Chest & back' }];
	let favoriteWorkoutRoutines = [
		{ id: 0, name: 'Full body' },
		{ id: 0, name: 'Chest & back' },
		{ id: 0, name: 'Arms & shoulders' }
	];
</script>

<Header />

<WorkoutRoutinesList title={'Scheduled today'} workoutRoutines={scheduledWorkoutRoutines} />
<WorkoutRoutinesList title={'Favourites'} workoutRoutines={favoriteWorkoutRoutines} />
