<template lang="jade">
  .introduction
    h1 Time to get calibrated
    p {{ msg }}
</template>

<script>
export default {
  data () {
    return {
      msg: 'This website will help you assess your 90% confidence interval. This means that if you make 10 statements and you\'re 90% sure each individual statement is true, you should be right 9 out of 10 times.'
    }
  }
}
</script>
