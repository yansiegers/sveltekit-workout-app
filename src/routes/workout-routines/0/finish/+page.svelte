<script lang="ts">
	import FloatingButton from '../../../../components/FloatingButton.svelte';
	import Header from '../../../../components/Header.svelte';
	import Icon from '../../../../components/Icon.svelte';
	import OrderableExercisesList from '../../../../components/OrderableExercisesList.svelte';

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
	let subHeading = 'Summary Friday 4th of August';

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

		<div class="mb-28">
			<OrderableExercisesList title="Warming up" exercises={warmingUpExercises} />
			<OrderableExercisesList title="Workout" exercises={workoutExercises} />

			<div class="flex justify-center">
				<button class="border-2 border-black bg-white px-3 py-2">
					<Icon name="plus" />
				</button>
			</div>

			<div class="mt-16 flex justify-center">
				<span class="text-center text-4xl">1:58:33</span>
			</div>
		</div>

		<FloatingButton text="Finish!" href="/workout-routines/0/exercises" />
	</main>
</div>
