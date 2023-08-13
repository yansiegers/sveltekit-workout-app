<script lang="ts">
	import Icon from './Icon.svelte';
	import SetButton from './SetButton.svelte';
	import Timer from './Timer.svelte';

	export let exercise: WorkoutExercise;

	let finishedSets = [24.1, 24.1];
	let setsCount = finishedSets.length > exercise.sets ? finishedSets.length : exercise.sets;
	let resting = true;

	interface WorkoutExercise {
		type: 'workoutExercise';
		sets: number;
		reps: number;
		name: string;
		weight: number;
	}
</script>

{#if resting}
	<Timer />
{:else}
	<p class="mb-3 text-center">{exercise.sets}x {exercise.reps} repetitions</p>
	<div class="flex flex-wrap justify-center gap-4">
		{#each Array(setsCount) as _, i}
			<SetButton>
				{#if finishedSets.length > i}
					<span><Icon name="check" size="2xl" /></span>
					<span>{finishedSets[i].toLocaleString()} kg</span>
				{:else if finishedSets.length <= i}
					<span class="text-2xl">{i + 1}</span>
				{/if}
			</SetButton>
		{/each}

		<SetButton>
			<span><Icon name="plus" size="2xl" /></span>
		</SetButton>
	</div>
{/if}
