<script>
	export let name;
	import Carousel from '@beyonk/svelte-carousel'
	import { ChevronLeftIcon, ChevronRightIcon } from 'svelte-feather-icons'
</script>

<main>
	<Carousel perPage={1} autoplay={3000}>
		<span class="control" slot="left-control">
			<ChevronLeftIcon />
		</span>
		<img src="media/whiteLeftLogo.jpeg" alt="Cobalt white mask" height="600">
		<img src="media/blueChemistry.jpeg" alt="Cobalt white mask" height="400">
		<span class="control" slot="right-control">
			<ChevronRightIcon />
		  </span>
	  </Carousel>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>