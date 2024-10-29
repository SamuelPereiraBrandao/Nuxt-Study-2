<template>
    <div class="ml-auto flex items-center">
      <nuxt-link v-for="(opcao, okey) in opcoes" :key="okey" :to="opcao.url" class="ml-2 hover:bg-white p-1 rounded-md" style="margin-right: 10px;">{{opcao.texto}}</nuxt-link>
    </div>
  </template>

  <script>
  export default {
      props:{
          opcoes: {
              type: Array,
              default: () => [
                  { texto: 'Home', url:'#'},
                  { texto: 'Produtos', url:'/produtos'},
                  { texto: 'Sobre', url:'/about'},
              ]
          }
      }
  }
  </script>
  
  <style scoped>
      .nuxt-link-exact-active {
      color: rgba(4, 61, 165, 0.904);
      }
  </style>