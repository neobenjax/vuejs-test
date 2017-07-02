<template>
  <div class="hello contenido">
    <div class="contenido-centrado">
      
      <div class="loading" v-if="!temporadas && temporadas.length < 0">
        <i class="material-icons spin">autorenew</i>
      </div>

      <div class="contenido-serie">


        <div class="temporadas" id="temporadas" v-if="temporadas && temporadas.length">

          <div class="temporada" v-for="temporada of temporadas">
            <div class="detalle-temporada">
              <img :src="temporada.image_large">
              <p class="titulo-temporada">{{temporada.title}}</p>
              <div class="ficha">
                <p><strong>Episodios: {{temporada.episodes_count}}</strong></p>
              </div>
            </div>

            <div class="episodios" v-if="temporada.episodes && temporada.episodes.length">
              
              <div class="episodio" v-for="episodio of temporada.episodes">
                
                <div class="imagen"><img :src="episodio.image_still"></div>
                
                <div class="detalle">
                  <p><strong>{{episodio.episode_number}}. {{episodio.description}}</strong></p>
                  
                  <p><strong>Año:</strong> {{episodio.year}} | {{episodio.rating_code}}</p>
                  
                  <p><strong>Duración:</strong> {{episodio.date}}</p>
                  
                  <div>
                    
                    <span><strong>Calificación:</strong> </span>
                    <ul class="rating">
                      <li v-for="n in parseInt(episodio.votes_average)">
                        <i class="material-icons">star</i>
                      </li>
                    </ul>

                  </div>

                </div>

                <div class="visto">
                  <button :class="{ visto: episodio.visto }">Visto <i class="material-icons">done</i></button>
                </div>

              </div>

            </div>

          </div>

        </div>

      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'home',
  data: () => ({
    temporadas: [],
    errors: [],
  }),

  created() {
    axios.get('https://www.mocky.io/v2/5957fe7b120000c801db7c85')
    .then((response) => {
      this.temporadas = response.data.response.seasons;
      for (let i = 0, n = this.temporadas.length; i < n; i += 1) {
        for (let j = 0, m = this.temporadas[i].episodes.length; j < m; j += 1) {
          this.temporadas[i].episodes[j].visto = false;
        }
      }
    })
    .catch((e) => {
      this.errors.push(e);
    });
  },

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
