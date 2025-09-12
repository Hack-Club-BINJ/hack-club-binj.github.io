<script setup lang="ts">
const { post } = defineProps<{
  post: Post
}>()
</script>

<template>
  <div class="card">
    <div class="card-body">
      <h3 class="card-title">{{ post.title }}</h3>
      <h6 class="card-subtitle mb-2 text-secondary">
        By {{ post.author }} on {{ new Date(post.date).toLocaleDateString() }}
      </h6>
      <div class="card-text" v-html="post.content"></div>
      <div v-if="post.images && post.images.length > 1" class="mt-3 d-flex gap-3 flex-wrap">
        <img
          v-for="(image, index) in post.images"
          :key="index"
          :src="image"
          class="img-fluid mb-2 rounded"
        />
      </div>
    </div>
    <img
      v-if="post.images && post.images.length === 1"
      :src="post.images[0]"
      class="card-img-bottom"
    />
  </div>
</template>
