<script lang="ts">
	export let workoutRoutine: { id: number; name: string };
	let workoutRoutineId = '/workout-routines/' + workoutRoutine.id.toString();
</script>

<a class="mb-4 block border-2 border-black p-4 text-2xl" href={workoutRoutineId}>
	{workoutRoutine.name}
</a>
