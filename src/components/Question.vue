<template lang="jade">
  li.question
    .text {{ text }}
    .inputs
      input.lower(type="text" v-model="lower")
      span to
      input.upper(type="text" v-model="upper")
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
      }
    }
  }
</script>

<style lang="scss">
  .inputs {
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
  }
</style>
