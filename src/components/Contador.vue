<template>
    <h3>Titulo contador!!!</h3>
    <p> {{ vrContador }} <sup> {{vrExponente}} </sup> = {{elevarC}} </p>
</template>

<script>
export default {
    name: 'Contador',
    data(){
        return{
            vrContador: 5,
            vrExponente : 2,
        }
    },
    methods: {
        elevar(){
            return this.vrContador ** this.vrExponente
        }
    },
    computed: {
        elevarC(){
            return this.vrContador ** this.vrExponente
        }
    }
}
</script>

<style>

</style>