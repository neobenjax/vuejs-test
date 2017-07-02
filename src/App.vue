<template>
  <div id="app" class="full">
      
    <header>
      <div class="contenido-centrado">
        <div class="logo">
          <img src="./assets/img/logo_brba.png">
        </div>
        <div class="buscador">
          <form action="">
            <input type="text" placeholder="Busca tu episodio">
            <button>
              <i class="material-icons">search</i>
            </button>
          </form>
        </div>
      </div>
    </header>

    <router-view></router-view>

    <footer>
      <div class="contenido-centrado">
        <p class="creditos">
          Benjamin Sánchez
        </p>
      </div>
    </footer>

  </div>
</template>

<script>
export default {
  name: 'app',
};
</script>
