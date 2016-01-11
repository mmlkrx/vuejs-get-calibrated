<template lang="jade">
  .container
    <introduction></introduction>
</template>

<script>
import Introduction from './components/Introduction.vue'

export default {
  components: {
    Introduction
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
