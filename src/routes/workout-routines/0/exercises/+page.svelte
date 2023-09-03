<script lang="ts">
	import ExerciseSets from '../../../../components/ExerciseSets.svelte';
	import FloatingButton from '../../../../components/FloatingButton.svelte';
	import Header from '../../../../components/Header.svelte';
	import Timer from '../../../../components/Timer.svelte';
	import WeightInput from '../../../../components/WeightInput.svelte';

	let subHeading = 'Up next: Pec Fly';
	let resting = false;

	let exercise: WorkoutExercise = {
		type: 'workoutExercise',
		sets: 4,
		reps: 10,
		name: 'Shoulder Press',
		weight: 24.1
	};

	interface WorkoutExercise {
		type: 'workoutExercise';
		sets: number;
		reps: number;
		name: string;
		weight: number;
	}
</script>

<div class="flex h-screen flex-col">
	<main class="h-full overflow-y-scroll p-8">
		<Header heading={exercise.name} {subHeading} exit={true} href="/" />

		{#if resting}
			<div class="mb-10 px-8">
				<Timer bind:resting />
			</div>

			<FloatingButton
				text="Rested!"
				href="?"
				on:click={() => {
					resting = false;
				}}
			/>
		{:else}
			<div class="mb-10">
				<ExerciseSets {exercise} bind:checked={resting} />
			</div>

			<FloatingButton text="Next exercise!" href="?" />
		{/if}

		<div class="mb-32">
			<WeightInput {exercise} />
		</div>
	</main>
</div>
