<script lang="ts">
	import { fly } from 'svelte/transition';
	export let refresh: URL;
</script>

{#key refresh}
	<div in:fly={{ x: -5, duration: 500, delay: 600 }} out:fly={{ x: 5, duration: 500 }}>
		<slot />
	</div>
{/key}
