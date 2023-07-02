 <script>
import PlaneIcon from "../../lib/assets/icons/plane.svg"
</script>
<div class="container">
<strong>Busca por ruta de vuelo</strong>
  <div class="inputContainer">
    <input type="search" placeholder="Origen"/>
    <img src={PlaneIcon} alt="Icono de un avión" />
    <input type="search" placeholder="Destino"/>
  </div>
</div>


<style>
  .container {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }
  .inputContainer {
    display: flex;
    align-items: center;
    gap: 1rem;
    width: 100%;
  }
</style>