<template lang="pug">
div(v-if="this.method")
  p.description {{method.description}}
  .demo-box(v-html="method.html", :ref="'demo'")
</template>

<script>
const METHODS = require('./METHODS.json');

export default {
  props: ['selected'],
  computed: {
    method() {
      try {
        const alignType = this.selected.split(':')[0];
        const alignMethod = this.selected.split(':')[1];
        return METHODS[alignType][alignMethod];
      }
      catch(error) {
        console.warn(error);
        return null;
      }
    },
  },
}
</script>

<style scoped lang="postcss">
.demo-box {
  background: #fafafa;
  padding: 2em;
}
</style>

<style lang="postcss">
.container {
  background: pink;
  height: 200px;
  margin: 0 auto;
}

.item {
  background: lightblue;
}
</style>
