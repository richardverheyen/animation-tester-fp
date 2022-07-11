<script lang="ts">
	import { each } from 'svelte/internal';

	type Card = {
		num: number;
	};

	let cards: Card[] = [
        {
			num: 0
		},
		{
			num: 1
		},
		{
			num: 2
		}
	];
</script>

<ul>
	{#each cards as card (card.num)}
		<li>{card.num}</li>
	{/each}
</ul>

<style lang="scss">
    ul {
        margin: auto;
        padding: 0;

        li {
            list-style: none;
        }
    }
</style>
