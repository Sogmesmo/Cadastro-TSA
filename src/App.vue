<template>
  <div id="app"> 
    <Menu/>
    <Cadastro/>
    <Footer/>
  </div>
</template>

<script>


import Menu from './components/Menu.vue'
import Cadastro from './components/Cadastro.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
   Menu,
   Cadastro,
   Footer
    
  }
}
</script>

<style>
</style>
