<template>
    <h3>Titulo contador!!!</h3>
    <p> {{ vrContador }} <sup> {{vrExponente}} </sup> = {{vrContador ** vrExponente}} </p>
</template>

<script>
export default {
    name: 'Contador',
    data(){
        return{
            vrContador: 5,
            vrExponente : 2,
        }
    }
}
</script>

<style>

</style>