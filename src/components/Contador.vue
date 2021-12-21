<template>
    <h3>{{ titulo }}</h3>
    <p> {{ vrContador }} <sup> {{vrExponente}} </sup> = {{elevarC}} </p>
    <div>
        <button @click="incrementar">+1</button>
        <button @click="decrementar">-1</button>
    </div>
</template>

<script>
export default {
    name: 'Contador',
    props: {
        titulo: String,
        start: {
            type: Number,
            default: 15,
            validator(val){
                return val > 100
            } 
        }
    },
    data(){
        return{
            vrContador:this.start,
            vrExponente : 2,
        }
    },
    methods: {
        incrementar(){
            this.vrContador++
        },
        decrementar(){
            this.vrContador--
        },
    },
    computed: {
        elevarC(){
            return this.vrContador ** this.vrExponente
        }
    }
}
</script>

<style>

button{
    background-color: rgb(76, 201, 163);
    border-radius: 5px;
    border: 1px solid gray;
    color: white;
    cursor: pointer;
    margin: 0 5px;
    padding: 5px 15px;
}
button:hover{
    background-color: rgb(68, 167, 137);
    transition: 0.2s ease-in-out;
}

</style>