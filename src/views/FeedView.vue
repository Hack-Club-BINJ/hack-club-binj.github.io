<script setup lang="ts">
import posts from '@/assets/posts.json'
import PostCard from '@/components/PostCard.vue'
</script>

<template>
  <div class="text-center bg-wavy pt-5 pb-5 mb-5">
    <h1>
      <span class="gradient-text">News Feed</span>
    </h1>
  </div>
  <div class="container">
    <div v-for="post in posts" :key="post.title">
      <PostCard class="mb-4" :post="post" />
    </div>
  </div>
  <div class="floatbar d-none d-sm-block">
    <RouterLink class="floatbtn btn btn-outline-primary rounded-circle opacity-50" to="/post">
      <i class="bi bi-file-earmark-plus-fill"></i>
    </RouterLink>
  </div>
</template>

<style scoped lang="scss">
.floatbar {
  position: fixed;
  bottom: 20px;
  right: 20px;
}
.floatbtn {
  width: 3rem;
  height: 3rem;
  display: flex;
  justify-content: center;
  align-items: center;
}
.floatbtn:hover {
  opacity: 1 !important;
  transition: all 0.3s;
}
</style>
