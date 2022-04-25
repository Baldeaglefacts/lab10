<template>
  <div id="app">
    <h1>Would you rather...</h1>
    <h2>Please make your choice!</h2>

    <div v-for="question in questions">
      <would-you-rather v-bind:id="question.id"
                        v-bind:question="question.wyrQuestion"
                        v-bind:answer1="question.wyrAnswer1"
                        v-bind:answer2="question.wyrAnswer2"
                        v-on:answer-changed="answerChanged">
      </would-you-rather>
    </div>

    <p>So, you have chosen...</p>
    <ul>
      <li>{{question1Answer}}</li>
      <li>{{question2Answer}}</li>
      <li>{{question3Answer}}</li>
    </ul>
    <p>... very interesting</p>
  </div>
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data(){
    return {
      questions: [
        {
          id: 1,
          wyrQuestion: 'Would you rather be a wizard or a superhero?',
          wyrAnswer1: 'Wizard',
          wyrAnswer2: 'Superhero',
        },
        {
          id: 2,
          wyrQuestion: 'Would you rather live in a place with a lot of trees or live in a place near the ocean?',
          wyrAnswer1: 'Trees',
          wyrAnswer2: 'Ocean',
        },
        {
          id: 3,
          wyrQuestion: 'Would you rather be incredibly lucky with average intelligence or incredibly smart with average luck?',
          wyrAnswer1: 'incredibly lucky',
          wyrAnswer2: 'incredibly smart'
        }
      ],
      question1Answer: '',
      question2Answer: '',
      question3Answer: '',
    }
  },
  methods: {
    answerChanged(choice, id) {
      if (id == 1) {this.question1Answer = choice}
      if (id == 2) {this.question2Answer = choice}
      if (id == 3) (this.question3Answer = choice)
      }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body {
  background: aquamarine;
}
h1 {
  text-shadow: 1px 1px 2px red, 0 0 1em blue, 0 0 0.2em blue;
}
</style>
