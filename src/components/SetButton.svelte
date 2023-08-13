<script lang="ts">
	export let checked = false;

	const check = () => (checked = true);
</script>

<button
	class="flex h-20 w-20 flex-col items-center justify-evenly border-2 border-black text-center"
	on:click={check}
>
	<slot />
</button>
