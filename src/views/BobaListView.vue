<script setup lang="ts">
import members from '@/assets/members.json'
import AvatarImage from '@/components/AvatarImage.vue'

const bobaMembers = members.filter((m) => m.boba)
</script>

<template>
  <div class="text-center bg-wavy pt-5 pb-5 mb-5">
    <h1>
      <span class="gradient-text">Boba Drops</span>
    </h1>
  </div>
  <div class="container">
    <div class="row flex-wrap g-2">
      <div class="col-12 col-md-6 col-lg-4" v-for="member in bobaMembers" :key="member.name">
        <div class="card">
          <a :href="member.boba" target="_blank">
            <img
              v-if="member.boba_image"
              :src="member.boba_image"
              class="card-img-top"
              :alt="`Image for ${member.name}`"
            />
          </a>
          <div class="card-body">
            <div class="card-title d-flex align-items-center">
              <AvatarImage :src="member.avatar" :alt="member.name" />
              <div>
                <h5 class="mb-1">{{ member.name }}</h5>
              </div>
            </div>
            <a class="card-link" :href="member.boba" target="_blank">View</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* https://stackoverflow.com/a/67356788/13951118 */
.card-img-top {
  width: 100%;
  height: 20vw;
  object-fit: contain;
}
</style>
