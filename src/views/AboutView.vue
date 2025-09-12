<script setup lang="ts">
import members from '@/assets/members.json'
</script>

<template>
  <div class="text-center bg-wavy pt-5 pb-5 mb-5">
    <h1>
      <span class="gradient-text">About Us</span>
    </h1>
  </div>
  <div class="container about-us-page">
    <h2>We are more than a coding club.</h2>
    <p>
      <strong><span class="gradient-text">Hack Club BINJ</span></strong> is proudly a member of the
      global 501(c)(3) nonprofit
      <strong
        ><a href="https://hackclub.com/" target="_blank" class="gradient-text gradient-hack-club"
          >Hack Club</a
        ></strong
      >, a community of high school coding clubs and makers around the world. This means we have
      access to a ton of resources, workshops, and events to help you grow as a coder and maker.
      Here are some things that we at Hack Club believe.<sup>*</sup>
    </p>
    <div class="row gy-4 my-4">
      <h2 class="col-12 col-lg-5" style="color: var(--purple)">Hack, hack, hack.</h2>
      <p class="col-12 col-lg-7">
        <strong>Hack Club will turn you into a hacker.</strong> We want a space at school where you
        and others can get together and make something that's interesting, every week. Hopefully, it
        will be your refuge from boring schoolwork!
      </p>
      <h2 class="col-12 col-lg-5" style="color: var(--blue)">Start building.</h2>
      <p class="col-12 col-lg-7">
        <strong>We believe the best way to learn is by making.</strong> Computer science courses
        teach you concepts - it's like trying to learn carpentry without any wood. So, here at Hack
        Club, you learn completely by building stuff. You start a complete beginner and build and
        ship something every meeting.
      </p>
      <h2 class="col-12 col-lg-5" style="color: var(--cyan)">Learn as you build.</h2>
      <p class="col-12 col-lg-7">
        <strong>The best carpenters didn't learn in the classroom.</strong> Nor did the best
        programmers. Through our workshops, we'll walk you through making your first projects.
        You'll be confused at the beginning, but you'll build understanding as you go. Also, we're
        always here to help!
      </p>
    </div>
    <small
      ><sup>*</sup> Text adapted from the
      <a href="https://hackclub.com/philosophy/" target="_blank">Hack Club Philosophy</a>.</small
    >
    <h2 class="mt-2">Club Members</h2>
    <div class="row">
      <div class="col-12 col-md-6 col-lg-4 mb-4" v-for="member in members" :key="member.name">
        <div class="card">
          <div class="card-body">
            <div class="card-title d-flex align-items-center">
              <img :src="member.avatar" class="rounded-circle avatar" :alt="member.name" />
              <div>
                <h5 class="mb-1">{{ member.name }}</h5>
                <h6 class="mb-0">{{ member.position }}</h6>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.about-us-page {
  font-size: 1.25rem;
}
.avatar {
  width: 50px;
  height: 50px;
  margin-right: 10px;
  object-fit: cover;
  vertical-align: middle;
}
</style>
