<template lang="jade">
  li.question
    p {{ text }}
    .row
      .inputs.column.column-50
        .row
          input.column.lower(type="text" v-model="lower")
          span to
          input.column.upper(type="text" v-model="upper")

</template>

<script>
  export default {
    data () {
      return {
        lower: '',
        upper: ''
      }
    },

    props: {
      text: String,
      correctAnswer: Number
    },

    computed: {
      answered () {
        return this.lower.length > 0 && this.upper.length > 0;
      },
      correct () {
        if (this.answered) {
          return (this.correctAnswer > this.lower && this.correctAnswer < this.upper) ? true : false;
        }
      }
    }
  }
</script>

<style lang="scss">
  span {
    margin: 0 2rem;
    line-height: 3.5rem;
  }

  .question {
    margin-bottom: 5rem;
  }
</style>
