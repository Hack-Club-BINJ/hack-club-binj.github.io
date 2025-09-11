<script setup lang="ts">
import { useRouter } from 'vue-router'
const router = useRouter()

// events

function onJoinClick() {
  router.push('/join')
}
</script>

<template>
  <div class="container-fluid">
    <div class="text-center bg-body-tertiary pt-5 pb-5 mb-5">
      <h1 style="font-size: 5em; font-weight: 700">
        <span class="text-primary outline-text-3" style="color: var(--color-primary-light)"
          >Welcome to</span
        >
        <br />
        <span class="gradient-text">Hack Club BINJ.</span>
      </h1>
      <div class="mt-4">
        <button class="btn btn-primary btn-lg" @click="onJoinClick">Join us!</button>
      </div>
    </div>
  </div>
  <div class="container">
    <div class="ps-4 pe-4 row">
      <div class="col-4">
        <p class="lead">
          The place where <span class="outline-text-2">magic</span>
          happens.
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.lead {
  font-size: 3rem;
  line-height: 1.2;
  text-align: end;
}
</style>
