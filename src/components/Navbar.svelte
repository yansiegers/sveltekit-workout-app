<script>
	import Icon from '../components/Icon.svelte';
</script>

<div class="flex justify-evenly border-t-2 border-black bg-white text-center">
	<div class="h-16 w-16 p-4">
		<Icon name="dumbbell" size="lg" />
	</div>
	<a class="h-16 w-16 p-4" href="/schedule">
		<Icon name="calendar" size="lg" />
	</a>
	<div class="absolute bottom-4 h-16 w-16 border-2 border-black bg-white p-4">
		<Icon name="plus" size="lg" />
	</div>
	<div class="h-16 w-16">
		<!-- placeholder -->
	</div>
	<a class="h-16 w-16 p-4" href="/">
		<Icon name="home" size="lg" />
	</a>
	<div class="h-16 w-16 p-4">
		<Icon name="user" size="lg" />
	</div>
</div>
