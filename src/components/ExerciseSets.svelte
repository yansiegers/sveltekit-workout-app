<script lang="ts">
	import Icon from './Icon.svelte';

	export let exercise: WorkoutExercise;

	let finishedSets = [24.1, 24.1];
	let setsCount = finishedSets.length > exercise.sets ? finishedSets.length : exercise.sets;

	interface WorkoutExercise {
		type: 'workoutExercise';
		sets: number;
		reps: number;
		name: string;
		weight: number;
	}
</script>

<p class="mb-3 text-center">{exercise.sets}x {exercise.reps} repetitions</p>
<div class="flex flex-wrap justify-center gap-4">
	{#each Array(setsCount) as _, i}
		<div class="flex h-20 w-20 flex-col justify-evenly border-2 border-black text-center">
			{#if finishedSets.length > i}
				<span><Icon name="check" size="2xl" /></span>
				<span>{finishedSets[i].toLocaleString()} kg</span>
			{:else if finishedSets.length <= i}
				<span class="text-2xl">{i + 1}</span>
			{/if}
		</div>
	{/each}

	<div class="flex h-20 w-20 flex-col justify-evenly border-2 border-black text-center">
		<span><Icon name="plus" size="2xl" /></span>
	</div>
</div>
