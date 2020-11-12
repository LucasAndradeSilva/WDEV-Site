<template>
  <div id="app">    
    <!-- Consulta de API precisa instalar um npm = npm install axios  -->
    <!-- Definição de rotas com o Vue deve instalar um npm = npm install vue-router -->
    <!-- Importando as Vues -->
    <Header />    
    <router-view path="$router.key" />
    <Footer/>
  </div>
</template>

<script>
import './styles/global.css';

import Header from './components/Header';
import Footer from './components/Footer';

export default {
  name: 'App',
  components: {
    Header,    
    Footer
  }
}
</script>

<style>

</style>


