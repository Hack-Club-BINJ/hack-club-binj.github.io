<script setup lang="ts">
import posts from '@/assets/posts.json'
</script>

<template>
  <div class="text-center bg-wavy pt-5 pb-5 mb-5">
    <h1>
      <span class="gradient-text">News Feed</span>
    </h1>
  </div>
  <div class="container">
    <div v-for="post in posts" :key="post.title">
      <div class="card mb-4">
        <div class="card-body">
          <h3 class="card-title">{{ post.title }}</h3>
          <h6 class="card-subtitle mb-2 text-secondary">
            By {{ post.author }} on {{ new Date(post.date).toLocaleDateString() }}
          </h6>
          <div class="card-text" v-html="post.content"></div>
          <div v-if="post.images && post.images.length > 1" class="mt-3">
            <img
              v-for="(image, index) in post.images"
              :key="index"
              :src="image"
              class="img-fluid mb-2"
            />
          </div>
        </div>
        <img
          v-if="post.images && post.images.length === 1"
          :src="post.images[0]"
          class="card-img-bottom"
        />
      </div>
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
