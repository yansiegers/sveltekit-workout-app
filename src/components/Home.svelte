<script>
	import WorkoutRoutinesList from './WorkoutRoutinesList.svelte';
	import Header from '../components/Header.svelte';

	let scheduledWorkoutRoutines = [{ id: 0, name: 'Chest & back' }];
	let favoriteWorkoutRoutines = [
		{ id: 0, name: 'Full body' },
		{ id: 0, name: 'Chest & back' },
		{ id: 0, name: 'Arms & shoulders' }
	];
	let otherWorkoutRoutines = [
		{ id: 0, name: 'Arms' },
		{ id: 0, name: 'Chest' },
		{ id: 0, name: 'Back' },
		{ id: 0, name: 'Shoulders' },
		{ id: 0, name: 'Core' },
		{ id: 0, name: 'Back' },
		{ id: 0, name: 'Legs' }
	];
</script>

<Header />

<WorkoutRoutinesList title={'Scheduled today'} workoutRoutines={scheduledWorkoutRoutines} />
<WorkoutRoutinesList title={'Favourites'} workoutRoutines={favoriteWorkoutRoutines} />
<WorkoutRoutinesList title={'Other workouts'} workoutRoutines={otherWorkoutRoutines} />
