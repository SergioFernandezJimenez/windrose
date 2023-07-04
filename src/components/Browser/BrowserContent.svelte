<script>
	import BrowserById from './BrowserById.svelte';
	import BrowserByRoute from './BrowserByRoute.svelte';

	let searchMethods = [
		{
			label: 'Busca por id',
			value: 1,
			component: BrowserById
		},
		{
			label: 'Busca por ruta',
			value: 2,
			component: BrowserByRoute
		}
	];

	let selectedSearchMethod = 1;

	const handleClick = (value) => {
		selectedSearchMethod = value;
	};
</script>

<div class="container">
	<h2>Encuentra cualquier vuelo</h2>
	<div class="tabContainer">
		<div class="buttonContainer">
			{#each searchMethods as searchMethod}
				<button
					on:click|preventDefault={() => handleClick(searchMethod.value)}
					class={selectedSearchMethod === searchMethod.value ? 'active' : ''}
					>{searchMethod.label}</button
				>
			{/each}
		</div>
		<div class="inputContainer">
			{#each searchMethods as searchMethod}
				{#if searchMethod.value === selectedSearchMethod}
					<svelte:component this={searchMethod.component} />
				{/if}
			{/each}
		</div>
	</div>
</div>

<style>
	.container {
		display: flex;
		flex-direction: column;
		margin: 0 auto;
		width: 450px;
		padding: 1rem;
		border: none;
		border-radius: 8px;
		box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
		position: absolute;
		top: 12rem;
		left: 0;
		right: 0;
		z-index: 1;
		background-color: #74d0c7ff;
	}
	h2 {
		color: #fff;
		display: flex;
		justify-content: center;
	}
	.tabContainer {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}
	.buttonContainer {
		display: flex;
		justify-content: center;
		gap: 0.5rem;
	}
	button {
		border: none;
		background: none;
		padding: 1rem;
		cursor: pointer;
		color: #fff;
		font-weight: bold;
		position: relative;
	}
	button::after {
		background: #fff;
		border-radius: 4px;
		content: '';
		display: none;
		height: 3px;
		width: 100%;
		left: 0;
		margin-top: 0.5rem;
		position: absolute;
	}

	.active::after {
		display: block;
	}
	.inputContainer {
		margin: 0.5rem;
	}
</style>
