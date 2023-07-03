<script>
	import BrowserById from "./BrowserById.svelte";
	import BrowserByRoute from "./BrowserByRoute.svelte";

  let searchMethods = [
    {
      label: "Busqueda por id",
      value: 1,
      component: BrowserById
    },
    {
      label: "Busqueda por ruta",
      value: 2,
      component: BrowserByRoute
    }
  ]

  let selectedSearchMethod = 1

  const handleClick = (value) => {
    selectedSearchMethod = value
  }
</script>

<div class="container">
  <div class="buttonContainer">
    {#each searchMethods as searchMethod}
      <button on:click|preventDefault={() => handleClick(searchMethod.value)} class={selectedSearchMethod === searchMethod.value ? 'active' : ''}>{searchMethod.label}</button>
    {/each}
  </div>
  <div>
    {#each searchMethods as searchMethod}
      {#if searchMethod.value === selectedSearchMethod}
          <svelte:component this={searchMethod.component} />
      {/if}
    {/each}
  </div>
</div>

<style>
  .container {
    min-width: 450px;
    padding: 1rem;
    border: 1px solid #eee;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }

  .buttonContainer {
    display: flex;
    justify-content: center;
    gap: .5rem;
  }

  button {
    border: none;
    background: none;
    padding: 1rem; 
    cursor: pointer;
  }
  
  .active {
    font-weight: bold;
  }
</style>