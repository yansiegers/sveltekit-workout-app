<script lang="ts">
	import Icon from './Icon.svelte';

	export let title: string;
	export let exercises: ExerciseType[];

	type ExerciseType = WorkoutExercise | WarmingUpExercise;
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

	function isWorkoutExercise(exerciseType: ExerciseType): exerciseType is WorkoutExercise {
		return exerciseType.type === 'workoutExercise';
	}
	function isWarmingUpExercise(exerciseType: ExerciseType): exerciseType is WarmingUpExercise {
		return exerciseType.type === 'warmingUpExercise';
	}
</script>

<div class="mb-2 font-bold">{title}</div>
<table class="w-full">
	{#each exercises as exercise}
		<tr>
			<td class="pb-6"><Icon name="grip-vertical" /></td>
			{#if isWarmingUpExercise(exercise)}
				<td class="pb-6">{exercise.distance}m</td>
				<td class="pb-6">{exercise.name}</td>
				<td class="pb-6" />
			{/if}
			{#if isWorkoutExercise(exercise)}
				<td class="pb-6">{exercise.sets}x {exercise.reps}</td>
				<td class="pb-6">{exercise.name}</td>
				<td class="pb-6">{exercise.weight.toLocaleString()}</td>
			{/if}
		</tr>
	{/each}
</table>
