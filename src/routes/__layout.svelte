<script lang="ts">
	import Header from '$lib/Header.svelte';
</script>

<Header />

<main>
	<slot />
</main>

<footer>
	<div class="gutters">
        svelte is great!
    </div>
</footer>

<style lang="scss">
    body {
		margin: 0;
	}

	:global(.gutters) {
		width: 100%;
		max-width: 1200px;
		box-sizing: border-box;
		padding: 0 3em;
		margin: auto;

		@media (max-width: 800px) {
			padding: 0 2em;
		}
		@media (max-width: 500px) {
			padding: 0 1em;
		}
	}
</style>