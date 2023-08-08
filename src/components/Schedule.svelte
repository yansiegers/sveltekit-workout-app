<script>
	import Header from './Header.svelte';
	import WorkoutRoutinesList from './WorkoutRoutinesList.svelte';

	let mondayWorkoutRoutines = [{ name: 'Legs' }];
	let wednesdayWorkoutRoutine = [{ name: 'Arms & shoulders' }];
	let fridayWorkoutRoutine = [{ name: 'Chest & back' }];

	let otherWorkoutRoutines = [{ name: 'Full body' }];
</script>

<Header heading="Schedule" />

<WorkoutRoutinesList title={'Monday'} workoutRoutines={mondayWorkoutRoutines} />
<WorkoutRoutinesList title={'Wednesday'} workoutRoutines={wednesdayWorkoutRoutine} />
<WorkoutRoutinesList title={'Friday'} workoutRoutines={fridayWorkoutRoutine} />
<WorkoutRoutinesList title={'Other workouts'} workoutRoutines={otherWorkoutRoutines} />
