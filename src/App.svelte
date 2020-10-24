<script>
	export let name;
	import Carousel from '@beyonk/svelte-carousel'
	import { ChevronLeftIcon, ChevronRightIcon } from 'svelte-feather-icons'
	import { LottiePlayer } from '@lottiefiles/svelte-lottie-player';
	import Navbar from "./components/Navbar.svelte"
	import Footer from "./components/Footer.svelte"
	import CTA from './components/CTA.svelte'
	import Dropdown from "./components/Dropdown.svelte"
	import Alert from './components/Alert.svelte'

	let clicked = false
	let showAlert = false

	let carousel
	let photoNames=['White mask', 'Blue mask']
	let photoName = photoNames[0]
	let userName = "Stranger"



	function handleLottieClick(event){
		
		if( userName!=='Stranger'){
			clicked=true
			showAlert=false
		}
			
		else {
			showAlert=true
		}
	}

	function handleCarousel(event){
		console.log(event.detail.currentSlide)
		photoName=photoNames[event.detail.currentSlide]

	}
	

	
</script>

<main>

	<Navbar/>
	{#if showAlert}
	<Alert/>
	{/if}
	{#if clicked === false  }
	<div on:click={handleLottieClick} class="goUp mx-auto w-2/3 md:w-1/2 lg:w-1/3">

		<LottiePlayer
		src="https://assets10.lottiefiles.com/packages/lf20_AQ3M8U.json"
		autoplay="{true}"
		loop="{true}"
		controls="{false}"
		renderer="svg"
		background="transparent"
	/>

	</div>
	<div class="md:w-1/2 w-7/12 mx-auto mb-4">
		<h1 class="text-3xl leading-9 font-extrabold tracking-tight cobaltBlueText sm:text-4xl sm:leading-10"> Welcome to ShipIt 2020!</h1>
		<h3 class="mt-4 text-gray-500 sm:text-4xl sm:leading-10" > Click on the animation to see our magnificent designs </h3>
		
	</div>

	<Dropdown bind:name={userName} bind:showAlert={showAlert}/>
	<p class="mt-2 text-3xl leading-9 font-extrabold tracking-tight cobaltBlueText sm:text-4xl sm:leading-10"> Hey, {userName}! </p>


	
	{:else }
	<h1 class="mb-8 text-2xl sm:text-3xl sm:leading-9 font-extrabold tracking-tight cobaltBlueText"> Which design do you like the most? </h1>
	<div class='w-9/12 mx-auto  '>
		<Carousel bind:this={carousel} on:change={handleCarousel} perPage={1} >
			<div class='w-full mx-auto'><img class="xl:w-5/12 md:w-1/2 md:mx-auto w-full" src="media/whiteLeftLogo.jpeg"  alt="Cobalt white mask"> 
				
			</div>
			<div class='w-full mx-auto'><img class="xl:w-5/12 md:w-1/2 md:mx-auto w-full" src="media/blueChemistry.jpeg"   alt="Cobalt blue mask"> 
			
			</div>
		</Carousel>
		<p class="mt-1 leading-9 text-gray-500 sm:text-2xl sm:leading-10" > {photoName} </p>
	</div>

	<CTA/>
	
	  {/if}
	  
	
</main>
{#if clicked === false}
<Footer/>
{:else}
<Footer/>
{/if}

<style>
	main {
		text-align: center;
	}


	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

	.goUp{
		margin-top: -4rem;
	}

</style>