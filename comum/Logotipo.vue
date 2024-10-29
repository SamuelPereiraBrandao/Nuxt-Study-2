<template>
    <div class="flex items-center">
        <div  style="margin-right: 10px;">
        <img :src="imagem" alt="" class=" border rounded-full" style="width: 40px; border-radius: 200px">
    </div>
    <div class="flex items-center w-full h-full ">
        <p class=" lobster">{{ texto }}</p>
    </div>
    </div>
</template>

<script>
export default {
    name:'LogoTipo',
    props: {
        imagem: {
            type: String,
            default: 'https://www.kasandbox.org/programming-images/avatars/starky-seed.png'
        },
        texto: {
            type: String,
            default: 'Loja Z'
        }
    }
}
</script>

<style>

</style>