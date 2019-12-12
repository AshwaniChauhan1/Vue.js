<template>
  <div>
    <input v-model="localMessage">
  </div>
</template>

<script>
export default {
  name: 'ChildComponent',
  data () {
    return {
      localMessage: this.message
    }
  },
  props: {
    message: {
      type: String,
      required: true
    }
  },
  watch: {
    localMessage (message) {
      this.$emit('update', message)
    }
  }
}
</script>