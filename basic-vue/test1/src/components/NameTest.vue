<template>
  <div>
    <input type="text" @input="updateName">
  </div>
</template>


<script>
export default {
  data() {
    return {
    name: ''
    }
  },
  methods: {
    updateName(e) {
      this.$emit('update-name',e.target.value)
    }
  },
}
</script>