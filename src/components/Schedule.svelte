<script lang="ts">
	import Header from './Header.svelte';
	import WorkoutRoutinesList from './WorkoutRoutinesList.svelte';

	let mondayWorkoutRoutines = [{ id: 0, name: 'Legs' }];
	let wednesdayWorkoutRoutine = [{ id: 0, name: 'Arms & shoulders' }];
	let fridayWorkoutRoutine = [{ id: 0, name: 'Chest & back' }];

	let otherWorkoutRoutines = [
		{ id: 0, name: 'Full body' },
		{ id: 0, name: 'Arms' },
		{ id: 0, name: 'Chest' },
		{ id: 0, name: 'Back' },
		{ id: 0, name: 'Shoulders' },
		{ id: 0, name: 'Core' },
		{ id: 0, name: 'Back' }
	];
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
