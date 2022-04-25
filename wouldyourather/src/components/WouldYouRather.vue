<template>
  <div class="wyr">
      <h3>{{id}}. {{ question }}</h3>

      <input type="radio" v-model="choice" v-bind:value="answer1" v-on:change="choiceMade"><label>{{answer1}}</label>
      <input type="radio" v-model="choice" v-bind:value="answer2" v-on:change="choiceMade"><label>{{answer2}}</label>
    </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  props: {
    id: Number,
    question: String,
    answer1: String,
    answer2: String
  },
  data() {
    return {
      choice: ''
    }
  },
  methods: {
    choiceMade() {
      this.$emit('answer-changed', this.choice, this.id)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
  color: white;
  text-shadow: 1px 1px 2px black;;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
