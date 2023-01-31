<template>
  <div class="app">
    <h3>Создать пост</h3>
    <form @submit.prevent>
      <input v-model="title" class="input" type="text"
             placeholder="Введите название">
      <input v-model="content" class="input" type="text"
             placeholder="Введите контент">
      <button @click="createPost" class="btn">Добавить</button>
    </form>

    <div class="posts">
      <h3>Список постов</h3>

      <div class="post" v-for="post in posts">
        <div><strong>Название:</strong> {{ post.title }}</div>
        <div><strong>Контент:</strong> {{ post.content }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      posts: [
        {id: Date.now(), title: 'Это название поста 1', content: 'Это контент поста 1'},
        {id: Date.now(), title: 'Это название поста 2', content: 'Это контент поста 2'},
        {id: Date.now(), title: 'Это название поста 3', content: 'Это контент поста 3'},
      ]
    }
  },

  methods: {
    createPost() {
      let newPost = {id: Date.now, title: this.title, content: this.content}

      this.posts.push(newPost)
      this.title = ''
      this.content = ''
    }
  }
}
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
  width: 80%;
  margin: 0 auto;

}

form {
  display: flex;
  flex-direction: column;
}

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

.posts {
  margin-top: 50px;
}

.post {
  padding: 15px;
  border: 1px solid teal;
  margin-top: 10px;
}
</style>
