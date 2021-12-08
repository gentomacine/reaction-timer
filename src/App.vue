<template>
 <div class="container">
  <h1> Ninja Reaction Timer </h1>
  
  <button @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Results v-if="showResults" :score="score"/>
  
  </div>
  
</template>s

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components: { Block, Results },
  data(){
    return{
      isPlaying:false,
      delay:null,
      score: null,
      showResults: false
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true,
      this.showResults=false
      

    },
    endGame(reactionTime){
      this.score= reactionTime
      this.isPlaying= false,
      this.showResults=true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align:center;}

  .container{
  color: #2c3e50;
  max-width: 800px;
  margin: 30px auto;
  overflow: auto;
  min-height:500px;
  border:1px solid steelblue;
  padding:30px;
  border-radius:5px;
  text-align: center;
  background: #f3f4f5;
  }
  button{
    background: #0fec3f;
    color:white;
    border:none;
    padding: 8px 16px;
    border-radius: 4px;
    font-size:16px;
    letter-spacing: 1px;
    cursor: pointer;
    margin: 10px;

  }
  button[disabled]{
    opacity: 0.2;
    cursor: not-allowed

  }

</style>
