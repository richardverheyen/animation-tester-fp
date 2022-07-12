<script lang="ts">
	import { each } from 'svelte/internal';

	type Card = {
		num: number;
	};

	let cards: Card[] = [... [...Array(40).keys()].map((k, i) => ({
		num: i
	}))
		
	];

    function indexToStyles(i:number) {
        return `animation-delay: ${cards.length - i - 1}s;
        transform: translateZ(${i}px) rotate3d(0.7, 0.2, -0.2, 60deg);
        transform-origin: 0 100% -${i}px;
        perspective-origin: 0 100% -${i}px;`;
    }
</script>

<ul>
	{#each cards as card (card.num)}
		<li style="{indexToStyles(card.num)}"></li>
	{/each}
</ul>

<style lang="scss">
	ul {
		position: relative;
		padding: 0;
        margin: auto;
		width: 210px;
		max-width: 18vw;
		height: 150px;
		perspective: 950px;
		filter: drop-shadow(0 2px 4px rgba(#000, 0.1));
		transition: all ease 200ms;

		@media (max-width: 500px) {
			position: absolute;
			top: 15%;
			right: -20px;
			transform: scale(0.8);
		}
		@media (max-width: 450px) {
			// transform: scale(0.95);
		}
		@media (max-width: 400px) {
			// transform: scale(0.92);
		}
		@media (max-width: 380px) {
			// transform: scale(0.90);
		}
		@media (max-width: 360px) {
			// transform: scale(0.88);
		}

		> li {
			list-style: none;
			position: absolute;
			bottom: 0;
			right: 0;
			width: 124px;
			height: 208px;
			border-radius: 10px;
			// box-shadow: 1px 5px 5px rgba(0, 0, 0, 0.05);
			cursor: pointer;
			transition: ease 500ms all;

			&:before {
				content: '';
				position: absolute;
				width: 124px;
				height: 208px;
				box-sizing: border-box;
				border-radius: 10px;
				box-shadow: 0px 2px 1px rgba(#000, 0.1);
				background-color: white;
				background: center/100px 30px no-repeat url('/floatplane-logo.png'),
					center/18px repeat url('/floatplane.png'), white;
				border: 4px white solid;
                // transform: translateZ(-20px) translateX(-50%) rotate3d(0.8, 0.2, -0.2, 66deg);
			}
		}

		&.animate li:nth-last-child(1):before,
		&.animate li:nth-last-child(2):before {
			animation-duration: 1s;
			animation-timing-function: ease;
			animation-iteration-count: 1;
			animation-direction: normal;
			animation-fill-mode: forwards;
			animation-delay: inherit;
		}
		&.animate li:nth-last-child(1):before {
			animation-name: slideBack;
		}
		&.animate li:nth-last-child(2):before {
			animation-name: slideForwards;
		}
		&.animate.reverse li:nth-last-child(1):before {
			animation-name: slideForwards;
		}
		&.animate.reverse li:nth-last-child(2):before {
			animation-name: slideBack;
		}

		@keyframes slideBack {
			0% {
				transform: translateY(0px);
			}
			70% {
				opacity: 1;
			}
			100% {
				transform: translateY(250px);
				opacity: 0;
			}
		}

		@keyframes slideForwards {
			0% {
				transform: translateY(0px);
			}
			80% {
				opacity: 1;
			}
			100% {
				transform: translateY(-250px);
				opacity: 0;
			}
		}
	}
</style>
