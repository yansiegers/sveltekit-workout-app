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
		<div class="p-4 w-16 h-16">W</div>
		<div class="p-4 w-16 h-16">S</div>
		<div class="p-4 w-16 h-16 border-2 border-black absolute bottom-4 bg-white">+</div>
		<div class="p-4 w-16 h-16" />
		<div class="p-4 w-16 h-16">H</div>
		<div class="p-4 w-16 h-16">A</div>
	</div>
</div>
