<script lang="ts">
	import Cards from '$lib/Cards.svelte';
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<div class="gutters">
	<h1>Home Page</h1>
	<Cards />

  <div class="view">
    <div class="cylinder-center">
      <div class="bottom" />
      <div class="middle" />
      <div class="top" />
    </div>
  </div>
	
</div>

<style lang="scss">
	div.gutters {
		display: flex;
		flex-direction: column;
		min-height: inherit;
	}

  .view {
    position: relative;
    width: 200px;
    height: 200px;
    perspective: 1000px;
    perspective-origin: center;
    margin: 200px;
  }
  .cylinder-center {
    position: absolute;
    top: 50%;
    left: 50%;
    width: 100px;
    height: 400px;
    background-color: blue;
    transform: translate3d(-50%, -50%, 200px) rotateX(20deg);
    transform-style: preserve-3d;

    > * {
      position: absolute;
      top: 50%;
      width: 100px;
      height: 100px;
    }

    > .top {
      background-color: rgb(240, 184, 88);
      border-radius: 50%;
      transform: translateY(-50%) rotateX(90deg) translateZ(150px);
    }

    > .middle {
      background-color: rgb(240, 88, 88);
      height: 300px;
      transform: translateY(-50%);
      background: linear-gradient(to left, black, white);
    }

    > .bottom {
      background-color: rgb(220, 240, 88);
      border-radius: 50%;
      transform: rotateX(90deg) translateZ(-150px);
    }
  }

</style>
