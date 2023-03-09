<template>
  <div class="app">
    <my-button @click="showDialog" style="margin-top: 20px">Создать пост</my-button>
    <my-dialog v-model:show="dialogVisible">
      <post-form @create="createPost"/>
    </my-dialog>
    <post-list :posts="posts" @remove="removePost"/>
  </div>
</template>

<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";
import MyDialog from "@/components/UI/MyDialog.vue";
import MyButton from "@/components/UI/MyButton.vue";

export default {
  name: "App",

  components: {
    MyButton,
    MyDialog,
    PostForm, PostList
  },

  data() {
    return {
      posts: [],

      dialogVisible: false
    }
  },

  methods: {
    createPost(post) {
      this.posts.push(post)
      this.dialogVisible = false
    },

    removePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id)
    },

    showDialog() {
      this.dialogVisible = true
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
