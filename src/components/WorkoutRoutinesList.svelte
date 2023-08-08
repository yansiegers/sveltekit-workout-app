<script lang="ts">
	import WorkoutRoutine from './WorkoutRoutine.svelte';

	export let title: string;
	export let workoutRoutines: { name: string }[];
</script>

<div class="mb-8">
	<h2 class="mb-2 font-bold">{title}</h2>

	{#each workoutRoutines as workoutRoutine}
		<WorkoutRoutine {workoutRoutine} />
	{/each}
</div>
