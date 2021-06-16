<template>
  <div id="app">
  
    <Nav />
    <Accueil/>
    <Competence />
    <Projet />
  </div>
</template>

<script>
import Nav from './components/Nav';
import Accueil from './components/Accueil.vue';
import Competence from './components/Competence.vue';
import Projet from './components/Projet.vue';

export default {
  name: 'App',
  components: {
    Nav,
    Accueil,
    Competence,
    Projet
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
  margin-top: 60px;
}
</style>
