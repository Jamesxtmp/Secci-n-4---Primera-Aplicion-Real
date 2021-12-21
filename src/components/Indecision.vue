<template>
  <img v-if="img" :src="img">
  <div class="bg-dark"></div>

  <div class="indecision-container">
    <input type="text" placeholder="Hazme una pregunta" v-model="boxValue">
    <p>Recuerda terminar con un signo de interrogacion (?)</p>
    <div v-if="bValid">
      <h2> {{boxValue}} </h2>
      <h3> {{respuesta}} </h3>
    </div>
  </div>

</template>

<script>
export default {
    name: 'Indecision',
    data(){
      return{
        boxValue: null,
        respuesta: null,
        img: null,
        bValid: false
      }
    },
    methods:{
      	async getGif(){
          this.respuesta = 'Pensando'
          const {answer, image} = await fetch('https://yesno.wtf/api').then(re => re.json())
          console.log(answer, image)
          this.respuesta = answer == 'no' ?'No' :'Si'
          this.img = image
        }
    },
    watch: {
      boxValue(val, oldval){
        this.bValid = false
        if(!val.includes('?')) return
        this.bValid = true
        this.getGif()
      }
    }
}
</script>

<style scoped>

    img, .bg-dark {
        height: 100vh;
        left: 0px;
        max-height: 100%;
        max-width: 100%;
        position: fixed;
        top: 0px;
        width: 100vw;
    }

    .bg-dark {
        background-color: rgba(0, 0, 0, 0.4);
    }

    .indecision-container {
        position: relative;
        z-index: 99;
    }
    
    input {
        width: 250px;
        padding: 10px 15px;
        border-radius: 5px;
        border: none;
    }
    input:focus {
        outline: none;
    }

    p {
        color: white;
        font-size: 20px;
        margin-top: 0px;
    }

    h3, h2 {
        color: white;
    }
    
    h2 {
        margin-top: 150px;
    }

</style>