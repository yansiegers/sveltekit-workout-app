<script lang="ts">
	import Icon from './Icon.svelte';

	export let heading = 'Workout app';
	export let subHeading = 'Friday 4th of August';
	export let exit = false;
	export let href = '';
</script>

<div class="relative mb-8">
	<h1 class="text-3xl font-bold">{heading}</h1>
	<div class="text-xl" role="doc-subtitle">{subHeading}</div>

	{#if exit}
		<a class="absolute right-0 top-0" {href}>
			<Icon name="xmark" size="2xl" />
		</a>
	{/if}
</div>
