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
@import "stylesheets/milligram";

body {
  -webkit-font-smoothing: antialiased !important;
}

.container {
  width: 50em;
  margin: 0 auto;
}

.row {
  margin-left: -.5rem;
}
</style>
