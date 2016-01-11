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
  font-family: Helvetica, sans-serif;
}

.container {
  width: 50em;
  margin: 0 auto;
}
</style>
