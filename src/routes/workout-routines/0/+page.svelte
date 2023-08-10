<script>
	import Header from '../../../components/Header.svelte';
	import Icon from '../../../components/Icon.svelte';

	let workoutRoutine = { id: 0, name: 'Chest & back' };
	let subHeading = 'Overview Friday 4th of August';
</script>

<div class="flex h-screen flex-col">
	<main class="h-full overflow-y-scroll p-8">
		<Header heading={workoutRoutine.name} {subHeading} />

		<div>
			<div class="mb-2 font-bold">Workout</div>
			<table class="w-full">
				<tr>
					<td><Icon name="grip-vertical" /></td>
					<td>4x 10</td>
					<td>Shoulder Press</td>
					<td>24,1</td>
				</tr>
			</table>
		</div>
	</main>
</div>
