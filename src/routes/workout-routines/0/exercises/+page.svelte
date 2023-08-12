<script lang="ts">
	import FloatingButton from '../../../../components/FloatingButton.svelte';
	import Header from '../../../../components/Header.svelte';
	import Icon from '../../../../components/Icon.svelte';

	let subHeading = 'Up next: Pec Fly';

	let exercise = {
		type: 'workoutExercise',
		sets: 4,
		reps: 10,
		name: 'Shoulder Press',
		weight: 24.1
	};
	let sets = [24.1, 24.1];
</script>

<div class="flex h-screen flex-col">
	<main class=" h-full overflow-y-scroll p-8">
		<Header heading={exercise.name} {subHeading} exit={true} href="/" />

		<FloatingButton text="Next exercise!" href="?" />

		<div class="mb-10">
			<p class="mb-3 text-center">{exercise.sets}x {exercise.reps} repetitions</p>
			<div class="flex flex-wrap justify-center gap-4">
				<div class="flex h-20 w-20 flex-col justify-evenly border-2 border-black text-center">
					<span><Icon name="check" size="2xl" /></span>
					<span>{sets[0].toLocaleString()} kg</span>
				</div>
				<div class="flex h-20 w-20 flex-col justify-evenly border-2 border-black text-center">
					<span><Icon name="check" size="2xl" /></span>
					<span>{sets[1].toLocaleString()} kg</span>
				</div>
				<div class="flex h-20 w-20 flex-col justify-evenly border-2 border-black text-center">
					<span class="text-2xl">3</span>
				</div>
				<div class="flex h-20 w-20 flex-col justify-evenly border-2 border-black text-center">
					<span class="text-2xl">4</span>
				</div>
				<div class="flex h-20 w-20 flex-col justify-evenly border-2 border-black text-center">
					<span><Icon name="plus" size="2xl" /></span>
				</div>
			</div>
		</div>

		<div>
			<p class="mb-3 text-center">Current weight</p>
			<div class=" flex items-center justify-center gap-4">
				<div class="border-2 border-black px-5 py-2"><Icon name="minus" size="xl" /></div>
				<input
					class="w-32 border-2 border-black px-4 py-3 text-center text-4xl"
					type="text"
					value={exercise.weight.toLocaleString()}
				/>
				<div class="border-2 border-black px-5 py-2"><Icon name="plus" size="xl" /></div>
			</div>
		</div>
	</main>
</div>
