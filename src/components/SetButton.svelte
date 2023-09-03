<script lang="ts">
	import SetIndicator from './SetIndicator.svelte';

	export let checked = false;

	const check = () => (checked = true);
</script>

<SetIndicator on:click={check}>
	<slot />
</SetIndicator>
