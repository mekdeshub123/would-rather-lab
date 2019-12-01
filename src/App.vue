<template>
  <div id="app">
    <Rather v-for="q in questions" v-bind:key=q.id
      v-bind:questions="q.question"
      v-bind:answer1="q.answer1"
      v-bind:answer2="q.answer2"
      v-bind:id="q.id"
      v-bind:selection-changed="selectionChanged">   

      </Rather>
       <h2>You would rather...</h2>
  <ul>
    <li v-for="choice in choices" v-bind:key="choice">{{choice}}</li>
  </ul>
  </div>
 
</template>

<script>
import Rather from './components/Rather.vue'

export default {
  name: 'app',
  data() {return {
    questions: [
      {
        id: 0,
        question: '...be a Tiger or Shark?',
        answer1: 'Be a tiger',
        answer2: 'Be a shark',
      },
      {
        id: 1,
        question: '...live on Mars or Jupiter?',
        answer1: 'Live on Mars',
        answer2: 'Live on Jupiter'
      },
      {
        id: 2,
        question: '...be a cat or squirtle?',
        answer1: 'Be a cat',
        answer2: 'Be a squirtle'
      }
    ],
    choices: [],
  }},
  components: {
    Rather   
  },
  methods: {
   selectionChanged(choice, id){
    console.log("selection changed", choice, id)
   }
  }
}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>