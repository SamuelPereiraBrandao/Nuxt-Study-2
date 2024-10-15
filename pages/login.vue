<template>
  <div>
    <h1 class="text-2xl text-center mt-2">Login</h1>
    <h1>Horário: {{ hora }}</h1>
    <nuxt-link to="/">Voltar para página inicial</nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'LoginPage',
  layout: 'no-nav',
  data() {
    return {

    };
  },
  
  head() {
    return {
      title: 'Login',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Conteúdo aqui ' + this.hora
        }
      ]
    };
  },

  computed: {
    hora(){
      const agora = new Date();
      const horas = agora.getHours();
      const minutos = agora.getMinutes();
      return (horas < 9? '0'+ horas:horas) + ":"+ (minutos< 9 ? '0' + minutos:minutos)
    }
  }
}
</script>
