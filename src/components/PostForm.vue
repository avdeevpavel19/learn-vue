<template>
  <h3>Создать пост</h3>
  <form @submit.prevent>
    <input v-model="post.title" class="input" type="text"
           placeholder="Введите название">
    <input v-model="post.content" class="input" type="text"
           placeholder="Введите контент">
    <button @click="createPost" class="btn">Добавить</button>
  </form>
</template>

<script>
export default {
  name: "PostForm",

  data() {
    return {
      post: {
        title  : '',
        content: ''
      }
    }
  },

  methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit('create', this.post)
      this.post = {
        title  : '',
        content: ''
      }
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

.btn {
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
  cursor: pointer;
  margin-top: 15px;
  width: 100%;
}
</style>
