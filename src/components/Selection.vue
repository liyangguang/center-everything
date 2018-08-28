<template lang="pug">
main
  h1 Center Everything!
  p Not using
    a(href="https://csswizardry.com/2012/11/code-smells-in-css/#magic-numbers", target="_blank") "magic numbers"
  div(v-for="(typeMethods, alignType) in methods")
    p {{alignType}}
    label(v-for="(_, method) in typeMethods")
      input(type="radio", :value="alignType + ':' + method", v-model="selected")
      | {{method}}
  Demo(:selected="selected")
</template>

<script>
import Demo from './Demo.vue'
const METHODS = require('./METHODS.json');

export default {
  components: {Demo},
  data() {
    return {
      methods: METHODS,
      selected: undefined,
    }
  },
}
</script>

<style scoped lang="postcss">

</style>
