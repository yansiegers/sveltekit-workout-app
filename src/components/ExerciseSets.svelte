<script lang="ts">
	import Icon from './Icon.svelte';
	import SetButton from './SetButton.svelte';
	import SetIndicator from './SetIndicator.svelte';

	export let exercise: WorkoutExercise;
	export let checked = false;

	let finishedSets = [24.1, 24.1];
	let setsCount = finishedSets.length > exercise.sets ? finishedSets.length : exercise.sets;

	interface WorkoutExercise {
		type: 'workoutExercise';
		sets: number;
		reps: number;
		name: string;
		weight: number;
	}

	function addSet() {
		setsCount++;
		console.log(setsCount);
	}
</script>

<p class="mb-3 text-center">{exercise.sets}x {exercise.reps} repetitions</p>
<div class="flex flex-wrap justify-center gap-4">
	{#each Array(setsCount) as _, i}
		{#if finishedSets.length > i}
			<SetIndicator>
				<span><Icon name="check" size="2xl" /></span>
				<span>{finishedSets[i].toLocaleString()} kg</span>
			</SetIndicator>
		{:else if finishedSets.length <= i}
			<SetButton bind:checked>
				<span class="text-2xl">{i + 1}</span>
			</SetButton>
		{/if}
	{/each}

	<SetIndicator on:click={addSet}>
		<span><Icon name="plus" size="2xl" /></span>
	</SetIndicator>
</div>
