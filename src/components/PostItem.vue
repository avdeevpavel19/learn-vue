<template>
  <div class="post">
    <div>
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Контент:</strong> {{ post.content }}</div>
    </div>

    <div class="post_btns">
      <my-button @click="$emit('remove', post)">Удалить</my-button>
    </div>
  </div>
</template>

<script>

export default {
  name: "PostItem",

  props: {
    post: {
      type    : Object,
      required: true
    }
  }
}
</script>

<style scoped>
.post {
  padding: 15px;
  border: 1px solid teal;
  margin-top: 10px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
