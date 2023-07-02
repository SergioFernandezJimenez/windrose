<script>
	import BrowserById from "./BrowserById.svelte";
	import BrowserByRoute from "./BrowserByRoute.svelte";

</script>
<div>
  <BrowserById/>
  <BrowserByRoute/>
</div>

<style>
  div {
    max-width: 500px;
    padding: 1rem;
    border: 1px solid #eee;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
</style>