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

	let currentWeight = exercise.weight;
	const step = 0.1;

	function addStepToCurrentWeight() {
		currentWeight += step;
	}
	function subtractStepToCurrentWeight() {
		currentWeight -= step;
	}
</script>

<p class="mb-3 text-center">Current weight</p>
<div class=" flex items-center justify-center gap-4">
	<button class="border-2 border-black px-5 py-2" on:click={subtractStepToCurrentWeight}
		><Icon name="minus" size="xl" /></button
	>
	<input
		class="w-32 border-2 border-black px-4 py-3 text-center text-4xl"
		type="text"
		value={currentWeight.toLocaleString()}
	/>
	<button class="border-2 border-black px-5 py-2" on:click={addStepToCurrentWeight}
		><Icon name="plus" size="xl" /></button
	>
</div>
