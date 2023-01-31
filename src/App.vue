<template>
  <div class="app">
    <post-form @create="createPost"/>
    <post-list :posts="posts"/>
  </div>
</template>

<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";

export default {
  name: "App",

  components: {
    PostForm, PostList
  },

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
    createPost(post) {
      this.posts.push(post)
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
</style>
