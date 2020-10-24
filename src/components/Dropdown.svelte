<script>

    let clicked = false
    export let name
    export let showAlert

    document.addEventListener('click' ,function(event){
        console.log(event.target.tagName)
        if(event.target.tagName !== 'svg' && event.target.tagName !== 'BUTTON' && event.target.tagName !== 'path')
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


<div class="w-56 mt-8 relative inline-block text-left">
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
  <div class="absolute origin-center mt-2 w-56 rounded-md shadow-lg">
    <div class="rounded-md bg-white shadow-xs">

      <div class="py-1 overflow-scroll h-24" role="menu" aria-orientation="vertical" aria-labelledby="options-menu">
        <a  id="Agota" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">Agota</a>
        <a  id="Alex" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">Alex</a>
        <a  id="Arthur" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">Arthur</a>
        <a  id="Clara" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">Clara</a>
        <a  id="Cristi" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">Cristi</a>
        <a  id="Halil" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">Halil</a>
        <a  id="Iris" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">Iris</a>
        <a  id="Marco" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">Marco</a>
        <a  id="Oana" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">Oana</a>
        <a  id="Roxana" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">Roxana</a>
        <a  id="Valentina" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">Valentina</a>
        <a  id="Vlad" on:click={handleOptionClick} class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:bg-gray-100 focus:text-gray-900" role="menuitem">Vlad</a>
      </div>
    </div>
  </div>
  {/if}
</div>