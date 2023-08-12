<script lang="ts">
	import Header from '../../../components/Header.svelte';
	import OrderableExercisesList from '../../../components/OrderableExercisesList.svelte';

	interface WorkoutExercise {
		type: 'workoutExercise';
		sets: number;
		reps: number;
		name: string;
		weight: number;
	}
	interface WarmingUpExercise {
		type: 'warmingUpExercise';
		distance: number;
		name: string;
	}

	let workoutRoutine = { id: 0, name: 'Chest & back' };
	let subHeading = 'Overview Friday 4th of August';

	let workoutExercises: WorkoutExercise[] = [
		{ type: 'workoutExercise', sets: 4, reps: 10, name: 'Shoulder Press', weight: 24.1 },
		{ type: 'workoutExercise', sets: 4, reps: 10, name: 'Pec Fly', weight: 59 },
		{ type: 'workoutExercise', sets: 4, reps: 10, name: 'Reverse Lat Pull', weight: 41.3 },
		{ type: 'workoutExercise', sets: 4, reps: 10, name: 'Bench Press', weight: 40 },
		{ type: 'workoutExercise', sets: 4, reps: 10, name: 'Incline Press', weight: 45.4 },
		{ type: 'workoutExercise', sets: 4, reps: 10, name: 'Supine Press', weight: 55.4 },
		{ type: 'workoutExercise', sets: 4, reps: 10, name: 'Decline Press', weight: 40 },
		{ type: 'workoutExercise', sets: 4, reps: 10, name: 'Lat Pulls', weight: 40 }
	];
	let warmingUpExercises: WarmingUpExercise[] = [
		{ type: 'warmingUpExercise', distance: 500, name: 'Rowing' }
	];
</script>

<div class="flex h-screen flex-col">
	<main class=" h-full overflow-y-scroll p-8">
		<Header heading={workoutRoutine.name} {subHeading} exit={true} href="/" />

		<div class="mb-24">
			<OrderableExercisesList title="Warming up" exercises={warmingUpExercises} />
			<OrderableExercisesList title="Workout" exercises={workoutExercises} />
		</div>

		<a
			class="absolute bottom-2 left-1/2 border-2 border-black bg-white px-5 py-4 text-2xl uppercase"
			style="transform: translate(-50%, -50%);"
			href="/workout-routines/0/exercises">Start</a
		>
	</main>
</div>
