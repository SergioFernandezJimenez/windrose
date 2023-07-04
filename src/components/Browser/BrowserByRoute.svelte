<script>
	import PlaneIcon from '../../lib/assets/icons/plane.svg';
</script>

<div class="container">
	<input type="search" placeholder="Origen" />
	<img src={PlaneIcon} alt="Icono de un avión" />
	<input type="search" placeholder="Destino" />
</div>

<style>
	.container {
		display: flex;
		justify-content: center;
		align-items: center;
	}
	input {
		border: none;
		border-radius: 10px;
		padding: 1rem;
	}
</style>
