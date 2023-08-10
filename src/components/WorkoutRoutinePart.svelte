<script lang="ts">
	import Icon from '../components/Icon.svelte';

	export let exercises: { sets: number; reps: number; name: string; weight: number }[];
</script>

<div class="mb-2 font-bold">Workout</div>
<table class="w-full">
	{#each exercises as exercise}
		<tr>
			<td><Icon name="grip-vertical" /></td>
			<td>{exercise.sets}x {exercise.reps}</td>
			<td>{exercise.name}</td>
			<td>{exercise.weight}</td>
		</tr>
	{/each}
</table>
