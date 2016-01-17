<template lang="jade">
  .questions
    h1 Questions
    ul
      <question
        v-for="question in questions"
        :text="question.text"
        :correctAnswer="question.correctAnswer">
      </question>
    .confidence-level(v-if="finished") Your current confidence level is {{ confidence }}0%
</template>

<script>
import Question from './Question.vue'

export default {
  components: {
    Question
  },

  data () {
    return {
      questions: [
        { text: 'In 1938 a British steam locomotive set a new speed record by going how fast? (km/h)', correctAnwser: 126, lower: '', upper: '' },
        { text: 'In what year did Newton publish the universal laws of gravitation?', correctAnwser: 1685, lower: '', upper: '' },
        { text: 'The Arpanet was established as a military communications system in what year?', correctAnwser: 1969, lower: '', upper: '' },
        { text: 'How many centimeter is a typical business card long?', correctAnwser: 8.89, lower: '', upper: '' },
        { text: 'What year was William Shakespeare born?', correctAnwser: 1564, lower: '', upper: '' },
        { text: 'What is the air distance between New York and Los Angeles in kilometer?', correctAnwser: 3945, lower: '', upper: '' },
        { text: 'What percentage of a square could be covered by a circle of the same width?', correctAnwser: 78.5, lower: '', upper: '' },
        { text: 'How old was Charlie Chaplin when he died?', correctAnwser: 88, lower: '', upper: '' },
        { text: 'How many pounds does a 350 page book weigh?', correctAnwser: 1.23, lower: '', upper: '' },
        { text: 'The TV show Gilligan\'s Island first aired in which year?', correctAnwser: 1964, lower: '', upper: '' }
      ]
    }
  },

  computed: {
    confidence () {
      var level = 0;
      this.questions.forEach(function(question) {
        if (question.correctAnwser > question.lower && question.correctAnwser < question.upper) {
          level++;
        }
      });
      return level;
    },
    finished () {
      answers = 0;
      this.questions.forEach(function(question) {
        if (question.lower.length > 0 && question.upper.length > 0) {
          answers++
        }
      });
      if (answers === 10) {
        return true;
      }

      return false;
    }
  }
}
</script>

<style lang="scss">
  ul {
    list-style-type: none;
    padding: 0;
  }

  .confidence-level {
    margin: 2em 0 6em 0;
    font-size: 2em;
  }
</style>
