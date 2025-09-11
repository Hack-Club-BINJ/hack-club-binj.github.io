<script setup lang="ts">
import { computed, ref } from 'vue'

const navbarCollapse = ref<HTMLElement | null>(null)

const isNavbarExpanded = computed(() => navbarCollapse.value?.classList.contains('show') || true)
</script>

<template>
  <nav class="navbar navbar-expand-lg bg-body-tertiary shadow-sm">
    <div class="container-fluid px-4">
      <RouterLink class="navbar-brand" to="/">
        <img
          src="@/assets/icon.png"
          alt="Logo"
          width="24"
          height="24"
          class="d-inline-block align-text-top me-2"
        />
        <strong class="title-gradient">Hack Club BINJ</strong>
      </RouterLink>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarCollapseContent"
        aria-controls="navbarCollapseContent"
        :aria-expanded="isNavbarExpanded"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div
        class="collapse navbar-collapse justify-content-end"
        id="navbarCollapseContent"
        ref="navbarCollapse"
      >
        <ul class="navbar-nav column-gap-4">
          <li class="nav-item">
            <RouterLink class="nav-link" to="/"><i class="bi bi-house-fill"></i> Home</RouterLink>
          </li>
          <li class="nav-item">
            <RouterLink class="nav-link" to="/about"
              ><i class="bi bi-info-circle-fill"></i> About</RouterLink
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
  <main class="container mt-4">
    <h1>Welcome to Hack Club BINJ</h1>
  </main>
</template>

<style scoped>
.title-gradient {
  background: linear-gradient(135deg, orange, red);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>
