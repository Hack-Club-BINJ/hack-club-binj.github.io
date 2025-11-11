<script setup lang="ts">
import projects from '@/assets/projects.json'
</script>

<template>
  <div class="text-center pt-5 pb-5 mb-5 bg-wavy">
    <h1>
      <span
        class="text-primary-light text-stroke-2 text-stroke-sm-3 text-stroke-md-4 text-stroke-lg-5"
        >Welcome to</span
      >
      <br />
      <span class="gradient-text">Hack Club BINJ.</span>
    </h1>
    <div class="d-flex justify-content-center align-items-center property-list">
      <span class="text-muted fs-5"><i class="bi bi-pin-map-fill"></i> BINJ C513</span>
      <span class="text-muted fs-5"><i class="bi bi-person-badge-fill"></i> David Wang</span>
    </div>
    <div class="mt-4 d-flex justify-content-center flex-wrap gap-4">
      <a class="btn btn-primary btn-lg" href="https://forms.office.com/r/1BPVp82suH" target="_blank"
        >Join us! <i class="bi bi-box-arrow-up-right"></i
      ></a>
      <a
        class="btn btn-outline-primary btn-lg"
        href="https://dashboard.hackclub.com/club-dashboard/290"
        target="_blank"
        >Dashboard <i class="bi bi-box-arrow-up-right"></i
      ></a>
      <a class="btn btn-outline-secondary btn-lg" href="https://hackclub.com/" target="_blank"
        >Learn about Hack Club <i class="bi bi-box-arrow-up-right"></i
      ></a>
    </div>
  </div>
  <div class="container">
    <div class="row gy-2">
      <div class="col-12 col-lg-3 text-lg-end text-primary">
        <h2 class="d-none d-lg-block">
          <span>Where</span> <br />
          <span class="text-stroke-2">growth</span> <br />
          <span>happens.</span>
        </h2>
        <h2 class="d-lg-none">
          <span>Where</span>
          <span class="text-stroke-2">growth</span>
          <span>happens.</span>
        </h2>
        <p class="text-secondary">* You learn best by making.</p>
      </div>
      <div class="col-12 col-lg-3">
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">Step 1. Workshops!</h5>
            <p class="card-text">
              We organize workshops for you to learn the basics of programming, such as how to make
              a website or a game. We bring Hack Club workshops such as
              <a href="https://boba.hackclub.com/" target="_blank"
                >Boba Drops <i class="bi bi-box-arrow-up-right"></i
              ></a>
              to you, where you not only learn, but also get cool rewards!
            </p>
          </div>
        </div>
      </div>
      <div class="col-12 col-lg-3">
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">Step 2. Projects!</h5>
            <p class="card-text">
              After the basics, we help you start your own coding projects. We guide you to think
              about real-world problems you are passionate about solving. If you need inspiration,
              we also introduce cool Hack Club events such as
              <a href="https://sprig.hackclub.com/" target="_blank"
                >Sprig <i class="bi bi-box-arrow-up-right"></i></a
              >!
            </p>
          </div>
        </div>
      </div>
      <div class="col-12 col-lg-3">
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">Step 3. Share!</h5>
            <p class="card-text">
              What's the point of making something if you don't share it with others? We encourage
              (and help!) you to share their projects, not only with the club, but also with the
              world, so that everyone can see and benefit from your hard work!
            </p>
          </div>
        </div>
      </div>
    </div>
    <h2 class="mt-4">What we've built</h2>
    <div class="row flex-wrap g-2">
      <div class="col-12 col-md-6 col-lg-4" v-for="project in projects" :key="project.name">
        <div class="card">
          <img
            v-if="project.image"
            class="card-img-top"
            :src="project.image"
            :alt="`Image for project ${project.name}`"
          />
          <div class="card-body">
            <h5 class="card-title">{{ project.name }}</h5>
            <p class="card-text">{{ project.description }}</p>
            <a
              class="card-link"
              :href="link.link"
              v-for="link in project.links || []"
              :key="link.name"
              >{{ link.name }}</a
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.property-list {
  margin-inline-start: 1rem;
  > span {
    margin-inline-end: 1rem;
    &:not(:first-child)::before {
      content: '•';
      margin-inline-end: 1rem;
    }
  }
}
/* https://stackoverflow.com/a/67356788/13951118 */
.card-img-top {
  width: 100%;
  object-fit: contain;
}
@media screen and (min-width: 768px) {
  .card-img-top {
    height: 20vw;
  }
}
</style>
