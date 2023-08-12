<script lang="ts">
	import Icon from './Icon.svelte';

	export let exercise: WorkoutExercise;

	interface WorkoutExercise {
		type: 'workoutExercise';
		sets: number;
		reps: number;
		name: string;
		weight: number;
	}
</script>

<p class="mb-3 text-center">Current weight</p>
<div class=" flex items-center justify-center gap-4">
	<div class="border-2 border-black px-5 py-2"><Icon name="minus" size="xl" /></div>
	<input
		class="w-32 border-2 border-black px-4 py-3 text-center text-4xl"
		type="text"
		value={exercise.weight.toLocaleString()}
	/>
	<div class="border-2 border-black px-5 py-2"><Icon name="plus" size="xl" /></div>
</div>
