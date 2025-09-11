<template>
  <div class="text-center bg-body-secondary pt-5 pb-5 mb-5">
    <h1 style="font-weight: 700">
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
    <div class="mt-4">
      <RouterLink class="btn btn-primary btn-lg me-4" to="/join">Join us!</RouterLink>
      <a class="btn btn-outline-secondary btn-lg" href="https://hackclub.com/" target="_blank"
        >Learn about Hack Club</a
      >
    </div>
  </div>
  <div class="container">
    <div class="ps-4 pe-4 row gy-2">
      <div class="col-12 col-lg-3 text-lg-end text-primary">
        <h2 class="d-none d-lg-block">
          Where <br />
          <span class="text-stroke-2">growth</span> <br />
          happens.
        </h2>
        <h2 class="d-lg-none">
          Where
          <span class="text-stroke-2">growth</span>
          happens.
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
              <a href="https://boba.hackclub.com/" target="_blank">Boba Drops</a> to you, where you
              not only learn, but also get cool rewards!
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
              <a href="https://sprig.hackclub.com/" target="_blank">Sprig</a>!
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
  </div>
</template>

<style scoped lang="scss">
.property-list {
  margin-inline-start: 1rem;
}
.property-list > span {
  margin-inline-end: 1rem;
}
.property-list > span:not(:first-child)::before {
  content: '•';
  margin-inline-end: 1rem;
}
</style>
