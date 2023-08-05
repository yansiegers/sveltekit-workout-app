<script>
	import ExercisesList from '../components/ExercisesList.svelte';
	import Header from '../components/Header.svelte';

	let favoriteExercises = [
		{ name: 'Full body' },
		{ name: 'Chest & back' },
		{ name: 'Arms & shoulders' }
	];
</script>

<Header />

<div class="mb-8">
	<h2 class="mb-2 font-bold">Scheduled today</h2>
	<div class="border-2 border-black p-4 mb-4 text-2xl">Chest & back</div>
</div>

<ExercisesList title={'Favourites'} exercises={favoriteExercises} />
