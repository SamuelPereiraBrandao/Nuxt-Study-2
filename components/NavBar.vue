<template>
  <div class="border rounded-md bg-blue-950 flex justify-around p-4 font-bold text-white m-1">
    <Logotipo />
   <AppMenu />    <!-- 
        <nuxt-link to="/">Home</nuxt-link>
        <nuxt-link to="/produtos">Produtos</nuxt-link>
        <nuxt-link to="/about">About</nuxt-link>
    -->
    <p class="ml-auto">
    <nuxt-link to="/login">Login</nuxt-link>
  </p> 
  </div>
</template>

<script>
import AppMenu from '../comum/AppMenu.vue';
import Logotipo from '../comum/Logotipo.vue';
export default {
  components: {
    Logotipo,
    AppMenu
  }

}
</script>

<style>

</style>