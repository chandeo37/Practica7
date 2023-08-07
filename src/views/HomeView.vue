<template>
  <div id="HomeView">

    <ListaComponent titulo="Lista de Cursos"/>
  </div>
</template>

<script>
// @ is an alias to /src
import ListaComponent from '@/components/ListaComponent.vue';

export default {
  name: 'HomeView',
  components: {
    ListaComponent
  }
}
</script>

<style scoped>
#HomeView{
  background-color:lightskyblue;
}
</style>
