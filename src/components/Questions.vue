<template lang="jade">
  .questions
    h2 Questions
    ul
      <question
        v-ref:questions
        v-for="question in questions"
        :text="question.text"
        :correct-answer="question.correctAnswer">
      </question>
    .status
      .confidence-level(v-if="finished") {{confidence}}0%
      .progress(v-else) {{ questionsAnswered }}
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
        { text: 'In 1938 a British steam locomotive set a new speed record by going how fast? (km/h)', correctAnswer: 126 },
        { text: 'In what year did Newton publish the universal laws of gravitation?', correctAnswer: 1685 },
        { text: 'The Arpanet was established as a military communications system in what year?', correctAnswer: 1969 },
        { text: 'How many centimeter is a typical business card long?', correctAnswer: 8.89 },
        { text: 'What year was William Shakespeare born?', correctAnswer: 1564 },
        { text: 'What is the air distance between New York and Los Angeles in kilometer?', correctAnswer: 3945 },
        { text: 'What percentage of a square could be covered by a circle of the same width?', correctAnswer: 78.5 },
        { text: 'How old was Charlie Chaplin when he died?', correctAnswer: 88 },
        { text: 'How many pounds does a 350 page book weigh?', correctAnswer: 1.23 },
        { text: 'The TV show Gilligan\'s Island first aired in which year?', correctAnswer: 1964 }
      ]
    }
  },

  computed: {
    confidence () {
      if (this.finished) {
        var level = 0;
        this.$refs.questions.forEach(function(question) {
          if (question.correct) {
            level++;
          }
        });
        return level;
      }
    },
    finished () {
      var answers = 0;
      this.$refs.questions.forEach(function(question) {
        if (question.answered) {
          answers++
        }
      });
      if (answers === this.questions.length) {
        return true;
      }

      return false;
    },
    questionsAnswered () {
      var allQuestions = this.questions.length;
      var answers = 0;
      this.$refs.questions.forEach(function(question) {
        if (question.answered) {
          answers++
        }
      });

      return answers + '/' + allQuestions;
    }
  }
}
</script>

<style lang="scss">
  ul {
    list-style-type: none;
  }
  .status {
    position: fixed;
    right: 80%;
    top: 11rem;
    height: 10em;
    width: 11em;
  }
  .progress, .confidence-level {
    color: #767C82;
    border: 8px dashed #D6D6D6;
    height: 100%;
    line-height: 3em;
    font-size: 3em;
    text-align: center;
    font-weight: bold;
  }
  .confidence-level {
    background-color: #78B580;
    border: 8px dashed #78B580;
    color: white;
  }
</style>
