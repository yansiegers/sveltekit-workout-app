<script lang="ts">
	export let name: string;
	export let size: '2xs' | 'xs' | 'sm' | '' | 'lg' | 'xl' | '2xl' = '';
	let faSize = size ? 'fa-' + size : '';
</script>

<i class="fa-solid fa-{name} {faSize}" />
