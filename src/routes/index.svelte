<svelte:head>
  <title>Home</title>
</svelte:head>

<script lang="ts">
	import Cards from '$lib/Cards.svelte';
</script>

<div class="gutters">
    <h1>Home Page</h1>
    <Cards />
</div>

<style lang="scss">
	div.gutters {
        display: flex;
        flex-direction: column;
        min-height: inherit;
    }
</style>