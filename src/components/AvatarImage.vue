<script setup lang="ts">
defineProps<{
  alt?: string
  src?: string
}>()
</script>

<template>
  <img :src="src" class="rounded-circle avatar" :alt="alt" v-if="src" />
  <img src="@/assets/avatar.jpg" class="rounded-circle avatar" :alt="alt" v-else />
</template>

<style scoped>
.avatar {
  width: 50px;
  height: 50px;
  margin-right: 10px;
  object-fit: cover;
  vertical-align: middle;
}
</style>
