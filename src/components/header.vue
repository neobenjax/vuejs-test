<template>

  <div class="header">
    <div class="contenido-centrado">
      <div class="logo">
        <img src="./assets/img/logo_brba.png">
      </div>
      <div class="buscador">
        <form action="">
          <input type="text" placeholder="Busca tu episodio" value="{{inputVal}}">
          <button>
            <i class="material-icons">search</i>
          </button>
        </form>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: 'header',
  data() {
    return {
      inputVal: 'Breaking Bad',
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
