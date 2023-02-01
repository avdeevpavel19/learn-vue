<template>
  <input :value="yoIsMyValue" @input="updateInput" class="input" type="text">
</template>

<script>
export default {
  name : "MyInput",
  props: {
    yoIsMyValue: [String],
  },

  methods: {
    updateInput(event) {
      this.$emit('update:yoIsMyValue', event.target.value)
    }
  }
}
</script>

<style scoped>
.input {
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
  width: 100%;
}
</style>
