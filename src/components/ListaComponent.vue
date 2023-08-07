<template>
  <div id="ListaComponent">
    <h1>{{ titulo }}</h1>
        <!-- <div class="tarjetas" v-for="curso in datos" v-bind:key="curso.id">  -->
        <div class="tarjetas" v-for="curso in consultarNoCompletados" v-bind:key="curso.id">
            <b-card
              v-bind:title="curso.nombre"
              v-bind:img-src="curso.img"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 20rem;"
              class="mb-2"
            >
              <b-card-text>
                {{ curso.descripcion }}
              </b-card-text>

              <b-card-text>
                Completado: <strong> {{ curso.completado}} </strong>
              </b-card-text>

              <b-button href="#" variant="primary">Go somewhere</b-button>
            </b-card>
      </div>


  </div>
</template>

<script>
import { mapState,mapActions, mapGetters } from 'vuex';
export default {
  name: 'ListaComponent',
  props: {
    titulo: String
  },
  data:function(){
    return{

    }
  },
  methods:{
    ...mapActions('datos_cursos',['consultarCursos']),
  },
  computed:{
    ...mapState('datos_cursos',['datos']),
    ...mapGetters('datos_cursos',['consultarNoCompletados']),
  },
  watch:{},
  created(){
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#ListaComponent{
  background-color: peachpuff;
  margin: 2%;
}

.tarjetas{
  display: inline-block;
  margin: 2%;
}
</style>
