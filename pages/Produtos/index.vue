<template>
  <div>
    <h1 class="text-2xl text-center mt-2">Produtos</h1>
    <div class="flex justify-center">
    <div v-if="produtos && produtos.length" class="flex flex-wrap justify-center w-10/12"> 
      <div v-for="(produto) in produtos" :key="produto.id" class="w-1/3 p-2">
          <nuxt-link :to="`/produtos/${produto.codigo}`">
            <div class="border p-4 text-center rounded">
            <h2 class="font-bold mb-4">{{ produto.titulo }}</h2>
            <img :src="produto.foto" alt="Imagem do produto" class="w-full max-h-60 object-cover rounded" />
            <p class="mt-2">{{ produto.descricao }}</p>
          <div class="my-4"><hr></div>
          <p>Preço: R$ {{ produto.preco }}</p>
        </div>
          </nuxt-link>
      </div>
    </div>
    <div v-else>
      <p class="text-center text-2xl font-semibold">Aguardando produtos...</p>
    </div>
  </div>
</div>
</template>
  <script>

  export default {
    name: 'ProdutosPage',
    asyncData(context) {
    return context.$axios.get('http://localhost:5000/produtos')
      .then(response => {
        return {
          produtos: response.data
        }
      })
      .catch(e => {
        context.error({ statusCode: 503, message: 'Não foi possível obter os dados, por favor tente novamente mais tarde' })
      })
  },
    head: {
      title:'Produtos',
    },

  }
  </script>
  