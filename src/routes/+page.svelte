<script>
	import Home from '../components/Home.svelte';
</script>

<div class="h-screen relative">
	<main class="p-8 mb-16">
		<Home />
	</main>
	<div
		class="border-t-2 border-black text-center flex justify-evenly fixed bottom-0 w-screen bg-white"
	>
		<div class="p-4 w-16 h-16"><i class="fa-solid fa-dumbbell fa-lg" /></div>
		<div class="p-4 w-16 h-16"><i class="fa-solid fa-calendar fa-lg" /></div>
		<div class="p-4 w-16 h-16 border-2 border-black absolute bottom-4 bg-white">
			<i class="fa-solid fa-plus fa-lg" />
		</div>
		<div class="p-4 w-16 h-16 fa-lg" />
		<div class="p-4 w-16 h-16"><i class="fa-solid fa-home fa-lg" /></div>
		<div class="p-4 w-16 h-16"><i class="fa-solid fa-user fa-lg" /></div>
	</div>
</div>
