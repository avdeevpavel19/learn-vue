<template>
  <h3>Создать пост</h3>
  <form @submit.prevent>
    <my-input v-model:yoIsMyValue="post.title" type="text" class="input"
              placeholder="Введите название"></my-input>
    <my-input v-model:yoIsMyValue="post.content" type="text" class="input"
              placeholder="Введите контент"></my-input>
    <my-button @click="createPost" class="btn" style="margin-top: 10px;">Добавить</my-button>
  </form>
</template>

<script>


import MyInput from "@/components/UI/MyInput.vue";

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
h3 {
  text-align: center;
  color: #34ebae;
  font-size: 23px;
  margin: 0;
}

form {
  margin-top: 10px;
  margin-right: auto;
  margin-left: auto;
  width: 100%;
}

.input {
  width: 93%;
  text-align: center;
  outline: 0 !important;
}

.btn {
  display: block;
}
</style>
