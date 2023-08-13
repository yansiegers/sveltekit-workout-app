<script lang="ts">
	export let checked = false;

	function check() {
		checked = true;
		console.log('checked from SetButton');
	}
</script>

<div
	class="flex h-20 w-20 flex-col justify-evenly border-2 border-black text-center"
	on:click={check}
>
	<slot />
</div>
