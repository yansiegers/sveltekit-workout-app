<script lang="ts">
	import Header from './Header.svelte';
	import WorkoutRoutinesList from './WorkoutRoutinesList.svelte';

	let mondayWorkoutRoutines = [{ name: 'Legs' }];
	let wednesdayWorkoutRoutine = [{ name: 'Arms & shoulders' }];
	let fridayWorkoutRoutine = [{ name: 'Chest & back' }];

	let otherWorkoutRoutines = [{ name: 'Full body' }];
</script>

<Header heading="Schedule" />

<section class="mb-24">
	<WorkoutRoutinesList title={'Monday'} workoutRoutines={mondayWorkoutRoutines} />
	<WorkoutRoutinesList title={'Wednesday'} workoutRoutines={wednesdayWorkoutRoutine} />
	<WorkoutRoutinesList title={'Friday'} workoutRoutines={fridayWorkoutRoutine} />
</section>

<section>
	<WorkoutRoutinesList title={'Other workouts'} workoutRoutines={otherWorkoutRoutines} />
</section>
