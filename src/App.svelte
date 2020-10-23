<script>
	export let name;
	import Carousel from '@beyonk/svelte-carousel'
	import { ChevronLeftIcon, ChevronRightIcon } from 'svelte-feather-icons'
	import Navbar from "./components/Navbar.svelte"
</script>

<main>
	<Navbar/>
	<Carousel perPage={1} >

		<img  src="media/whiteLeftLogo.jpeg" alt="Cobalt white mask" >
		<img  src="media/blueChemistry.jpeg" alt="Cobalt blue mask" >

	  </Carousel>
	
</main>

<style>
	main {
		text-align: center;
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