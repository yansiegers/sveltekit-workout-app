<script lang="ts">
	import FloatingButton from '../../../../components/FloatingButton.svelte';
	import Header from '../../../../components/Header.svelte';
	import Icon from '../../../../components/Icon.svelte';

	let exercise = { id: 0, name: 'Shoulder Press' };
	let subHeading = 'Up next: Pec Fly';
</script>

<div class="flex h-screen flex-col">
	<main class=" h-full overflow-y-scroll p-8">
		<Header heading={exercise.name} {subHeading} exit={true} href="/" />

		<FloatingButton text="Next exercise!" href="?" />

		<div class="flex flex-wrap justify-center gap-4">
			<div class="flex h-20 w-20 flex-col justify-evenly border-2 border-black text-center">
				<span><Icon name="check" size="2xl" /></span>
				<span>24,1 kg</span>
			</div>
			<div class="flex h-20 w-20 flex-col justify-evenly border-2 border-black text-center">
				<span><Icon name="check" size="2xl" /></span>
				<span>24,1 kg</span>
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
	</main>
</div>
