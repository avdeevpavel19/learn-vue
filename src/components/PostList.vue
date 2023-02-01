<template>
  <div class="posts">
    <h3>Список постов</h3>
    <post-item v-for="post in posts" :post="post" :key="post.id" @remove="$emit('remove', post)"/>
  </div>
</template>

<script>
import PostItem from "@/components/PostItem.vue";

export default {
  name: "PostList",

  components: {
    PostItem
  },

  props: {
    posts: {
      type    : Array,
      required: true
    }
  }
}
</script>

<style scoped>
.posts {
  margin-top: 50px;
}
</style>
