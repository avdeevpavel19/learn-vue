<template>
  <div class="posts" v-if="posts.length > 0">
    <h1 class="postList">Список постов</h1>
    <post-item v-for="post in posts" :post="post" :key="post.id" @remove="$emit('remove', post)"/>
  </div>

  <h1 class="postNotFound" v-else>Постов нет</h1>
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
.postList {
  text-align: center;
  color: #34ebae;
}

.postNotFound {
  text-align: center;
  margin-top: 50px;
  color: #f57e42;
}
</style>
