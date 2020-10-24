<script>

    let clicked = false
    export let name
    export let showAlert

    document.addEventListener('click' ,function(event){
        if(event.target.tagName !== 'svg' && event.target.tagName !== 'BUTTON')
        clicked = false
    })

    function handleButtonClick(){
        clicked=!clicked
    }
    function handleOptionClick(event){
        clicked=false;
        console.log(event.target.id)
        name=event.target.id
        showAlert = false

    }
</script>


<div class="relative inline-block text-left">
  <div>
    <span class="rounded-md shadow-sm">
      <button on:click={handleButtonClick} type="button" class="inline-flex justify-center w-full rounded-md border border-gray-300 px-4 py-2 bg-white text-sm leading-5 font-medium text-gray-700 hover:text-gray-500 focus:outline-none focus:border-blue-300 focus:shadow-outline-blue active:bg-gray-50 active:text-gray-800 transition ease-in-out duration-150" id="options-menu" aria-haspopup="true" aria-expanded="true">
        {name === 'Stranger' ? 'Who are you?' : name}
        <!-- Heroicon name: chevron-down -->
        <svg class="-mr-1 ml-2 h-5 w-5" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
          <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
        </svg>
      </button>
    </span>
  </div>

  <!--
    Dropdown panel, show/hide based on dropdown state.

    Entering: "transition ease-out duration-100"
      From: "transform opacity-0 scale-95"
      To: "transform opacity-100 scale-100"
    Leaving: "transition ease-in duration-75"
      From: "transform opacity-100 scale-100"
      To: "transform opacity-0 scale-95"
  -->
  {#if clicked}
  <div class="origin-top-right absolute right-0 mt-2 w-56 rounded-md shadow-lg">
    <div class="rounded-md bg-white shadow-xs">

      <div class="py-1" role="menu" aria-orientation="vertical" aria-labelledby="options-menu">
        <a  id="one" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">Account settings</a>
        <a  id="two" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">Support</a>
        <a  id="three" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">License</a>

      </div>
    </div>
  </div>
  {/if}
</div>