<script lang="ts">
	import Icon from '../components/Icon.svelte';

	export let title: string;
	export let exercises: { sets: number; reps: number; name: string; weight: number }[];
</script>

<div class="mb-2 font-bold">{title}</div>
<table class="w-full">
	{#each exercises as exercise}
		<tr>
			<td class="pb-6"><Icon name="grip-vertical" /></td>
			<td class="pb-6">{exercise.sets}x {exercise.reps}</td>
			<td class="pb-6">{exercise.name}</td>
			<td class="pb-6">{exercise.weight}</td>
		</tr>
	{/each}
</table>
