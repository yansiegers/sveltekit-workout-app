<script>
	import ExercisesList from '../components/ExercisesList.svelte';
	import Header from '../components/Header.svelte';

	let scheduledExercises = [{ name: 'Chest & back' }];
	let favoriteExercises = [
		{ name: 'Full body' },
		{ name: 'Chest & back' },
		{ name: 'Arms & shoulders' }
	];
</script>

<Header />

<ExercisesList title={'Scheduled today'} exercises={scheduledExercises} />
<ExercisesList title={'Favourites'} exercises={favoriteExercises} />
