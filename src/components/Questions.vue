<template lang="jade">
  .questions
    h1 Questions
    ul
      li.question(v-for="question in questions")
        .text {{ question.text }}
        form
          input.lower(type="text")
          span to
          input.upper(type="text")
          input(type="submit")
</template>

<script>
export default {
  data () {
    return {
      questions: [
        { text: 'In 1938 a British steam locomotive set a new speed record by going how fast? (km/h)', correctAnwser: 126 },
        { text: 'In what year did Newton publish the universal laws of gravitation?', correctAnwser: 1685 },
        { text: 'The Arpanet was established as a military communications system in what year?', correctAnwser: 1969 },
        { text: 'How many centimeter is a typical business card long?', correctAnwser: 8.89 },
        { text: 'What year was William Shakespeare born?', correctAnwser: 1564 },
        { text: 'What is the air distance between New York and Los Angeles in kilometer?', correctAnwser: 3945 },
        { text: 'What percentage of a square could be covered by a circle of the same width?', correctAnwser: 78.5 },
        { text: 'How old was Charlie Chaplin when he died?', correctAnwser: 88 },
        { text: 'How many pounds does a 350 page book weigh?', correctAnwser: 1.23 },
        { text: 'The TV show Gilligan\'s Island first aired in which year?', correctAnwser: 1964 }
      ]
    }
  }
}
</script>

<style lang="scss">
  ul {
    list-style-type: none;
    padding: 0;

    form {
      margin: 1em 0 2.5em 0;

      input { vertical-align: top; }

      input[type="text"] {
        padding-left: 1em;
        height: 3em;
        border-radius: 2px;
        border: 1px solid #C3C3C3;
      }

      .lower {
        margin-right: 1em;
      }

      span {
        vertical-align: -webkit-baseline-middle;
      }

      .upper {
        margin: 0 1em;
      }

      input[type="submit"] {
        padding: .6em 1em;
        border: 0;
        background-color: #4BC74B;
        color: white;
        font-size: 1em;
        border-radius: 2px;

        &:hover {
          background-color: darken(#4BC74B, 10%);
          cursor: pointer;
        }
      }
    }
  }
</style>
