<template lang="jade">
  .container
    <introduction></introduction>
    <questions></questions>
</template>

<script>
import Introduction from './components/Introduction.vue'
import Questions from './components/Questions.vue'

export default {
  components: {
    Introduction,
    Questions
  }
}
</script>

<style lang="scss">
body {
  font-family: 'Lato', sans-serif;
  -webkit-font-smoothing: antialiased !important;
}

.container {
  width: 50em;
  margin: 0 auto;
}
</style>
