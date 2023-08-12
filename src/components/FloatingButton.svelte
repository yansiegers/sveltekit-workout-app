<script lang="ts">
	export let text: string;
	export let href: string;
</script>

<a
	class="absolute bottom-2 left-1/2 w-max border-2 border-black bg-white px-5 py-4 text-center text-2xl uppercase"
	style="transform: translate(-50%, -50%);"
	{href}>{text}</a
>
