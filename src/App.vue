<template>
  <div id="app">

    <!-- BARRA DE NAVEGACION-->
<div>
  <b-navbar toggleable="lg" type="dark" variant="primary">
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-navbar-brand href="#"> <router-link to="/">Home</router-link> </b-navbar-brand>
        <b-navbar-brand href="#"> <router-link to="/administracion">Administracion</router-link> </b-navbar-brand>
        <b-navbar-brand href="#"> <router-link to="/about">About</router-link> </b-navbar-brand>
        <b-nav-item href="#">Link</b-nav-item>
        <b-nav-item href="#" disabled>Disabled</b-nav-item>
      </b-navbar-nav>

    </b-collapse>
  </b-navbar>
</div>
<!-- FIN BARRA DE NAVEGACION-->



    <router-view/>
  </div>
</template>

<script>
import { mapActions } from 'vuex';
export default{
  name: 'app',
  data:function(){
    return{

    }
  },
  props:{},
  components:{},
  methods:{
    ...mapActions('datos_cursos',['consultarCursos', 'consultarDatosTabla']),
  },
  computed:{},
  watch:{},
  beforeMount(){
    this.consultarCursos();
    this.consultarDatosTabla();
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
