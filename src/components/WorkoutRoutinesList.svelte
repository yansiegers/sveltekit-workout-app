<script lang="ts">
	export let title: string;
	export let workoutRoutines: { name: string }[];
</script>

<div class="mb-8">
	<h2 class="mb-2 font-bold">{title}</h2>

	{#each workoutRoutines as { name }}
		<div class="border-2 border-black p-4 mb-4 text-2xl">{name}</div>
	{/each}
</div>
