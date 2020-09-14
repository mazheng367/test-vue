<template>
  <input v-bind="$attrs" :value="value"/>
</template>

<script>
export default {
  name: "DInput",
  props: {
    value: {
      type: String
    }
  },
  data() {
    return {
      attrs1: {}
    }
  },
  created() {
    this.attrs = this.$attrs;
  }
}
</script>

<style scoped>

</style>