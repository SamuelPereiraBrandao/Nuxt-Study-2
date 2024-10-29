<template>
  <div>
    <div class="ml-4">
    <nuxt-link :to="`/produtos`">
    <span class="mdi mdi-arrow-left-circle text-2xl"></span>
    </nuxt-link>
    <p class="mb-4">Detalhes do Produto</p>
  </div>
    <div v-if="!$fetchState.error || !produto" class="flex justify-center">
      <div class="w-10/12">
      <p>Cod: {{ produto.codigo }}</p>
      <p>{{ produto.titulo }}</p>
      <p>Preço: R$ {{ produto.preco }}</p>
      <div class="overflow-hidden rounded flex justify-center" style="max-height: 500px;">
      <img :src="produto.foto" alt="" class="  object-cover" >
    </div>
      <p>{{ produto.descricao }}</p>
      <div class="flex justify-center mt-4">
        <nuxt-link :to="`/produtos`">
        <div class="font-weight-bold border-2  py-2 px-10 cursor-pointer hover:bg-black/5 transition-all rounded">
      <p>Comprar</p>
    </div>
  </nuxt-link>
    </div>
    </div>
    </div>
    <div v-else>
      <p>Não foi possível carregar os ados do Produto. Por favor tente mais tarde !</p>
      <p>Error: {{ $fetchState.error.message }}</p>
    </div>
  </div>
</template>

<script>
import "@mdi/font/css/materialdesignicons.css";
export default {
  
  data() {
    return {
      produto: {}
    }
  },
  fetch() {
    return this.$axios.get(`http://localhost:5000/produtos?codigo=${this.codg_prod}`).then(response => {
      this.produto = response.data[0];
      return true;
    })
  },
  computed: {
    codg_prod() {
      return this.$route.params.codigo;
    }
  }

}
</script>

<style></style>