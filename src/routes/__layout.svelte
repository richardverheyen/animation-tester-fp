<script lang="ts">
	import Header from '$lib/Header.svelte';
</script>

<header>
    <Header />
</header>

<main>
	<slot />
</main>

<footer>
	<div class="gutters">svelte is great!</div>
</footer>

<style lang="scss">
    header {
        height: 60px;
    }
	main {
		min-height: calc(100vh - 60px - 60px);
	}
    footer {
        display: flex;
        align-items: center;
        height: 60px;
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
