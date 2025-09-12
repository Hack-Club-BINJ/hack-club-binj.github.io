<script setup lang="ts">
import posts from '@/assets/posts.json'
import PostCard from '@/components/PostCard.vue'
import { computed, ref } from 'vue'

const title = ref('')
const author = ref('')
const content = ref('')
const imageUrls = ref<string[]>([''])

const newPost = computed(() => {
  return {
    author: author.value,
    title: title.value,
    date: currentDate.value,
    content: content.value,
    images: imageUrls.value.filter((url) => !!url),
  }
})

const shouldShowPreview = computed(() => {
  return !!title.value || !!author.value || !!content.value
})

const currentDate = computed(() => {
  const date = new Date()
  return `${date.getFullYear()}-${(date.getMonth() + 1).toString().padStart(2, '0')}-${date.getDate().toString().padStart(2, '0')}`
})

const updatedPosts = computed(() => {
  if (!title.value || !author.value || !content.value) return null
  return [newPost.value].concat(posts)
})

const displayUpdatedPosts = computed(() => {
  if (!updatedPosts.value) return null
  return JSON.stringify(updatedPosts.value, null, 4)
})

// events

function onRemoveImage(index: number) {
  imageUrls.value.splice(index, 1)
}

function onAddImage() {
  imageUrls.value.push('')
}
</script>

<template>
  <div class="text-center bg-wavy pt-5 pb-5 mb-5">
    <h1>
      <span class="gradient-text">New Post</span>
    </h1>
  </div>
  <div class="container">
    <p>
      This form will not actually create the post, but rather generate the JSON content for you to
      open a PR on
      <a href="https://github.com/Hack-Club-BINJ/hack-club-binj.github.io">our GitHub repo</a>!
    </p>
    <div class="mb-3">
      <label class="form-label fw-semibold" for="inputTitle">Title</label>
      <input
        class="form-control"
        id="inputTitle"
        type="text"
        placeholder="I made a cool Orpheus website!"
        required
        v-model="title"
      />
    </div>
    <div class="mb-3">
      <label class="form-label fw-semibold" for="inputAuthor">Author</label>
      <input
        class="form-control"
        id="inputAuthor"
        type="text"
        placeholder="John Smith"
        required
        v-model="author"
      />
    </div>
    <div class="mb-3">
      <label class="form-label fw-semibold" for="inputContent">Post content (HTML allowed!)</label>
      <textarea
        class="form-control"
        id="inputContent"
        placeholder="Today, during our club meeting, I created this really great website..."
        required
        style="height: 10rem"
        v-model="content"
      ></textarea>
    </div>
    <div class="mb-3">
      <label class="form-label fw-semibold" for="inputImage0">Images</label>
      <div class="input-group mb-3" v-for="(url, index) in imageUrls" :key="index">
        <input
          class="form-control"
          :id="`inputImage${index}`"
          type="url"
          placeholder="Enter image URL (you can upload images on Slack in #cdn)"
          v-model="imageUrls[index]"
        />
        <button
          class="btn btn-outline-danger"
          @click="onRemoveImage(index)"
          v-if="imageUrls.length > 1"
        >
          <i class="bi bi-trash-fill"></i>
        </button>
        <button class="btn btn-outline-success" @click="onAddImage" v-if="index === 0">
          <i class="bi bi-plus-square"></i>
        </button>
      </div>
    </div>
    <div v-if="shouldShowPreview">
      <h2>Preview</h2>
      <PostCard class="mb-3" :post="newPost" />
    </div>
    <div v-if="updatedPosts">
      <h2>How to add this post</h2>
      <ol>
        <li>
          If you haven't already,
          <a href="https://github.com/signup" target="_blank">sign up for a GitHub account</a>.
        </li>
        <li>
          Go to the
          <a
            href="https://github.com/Hack-Club-BINJ/hack-club-binj.github.io/blob/main/src/assets/posts.json"
            target="_blank"
            ><code>/src/assets/posts.json</code></a
          >
          file in the website's repo.
        </li>
        <li>
          Click on the edit button with a pencil as the icon in the editor toolbar.
          <em>(If GitHub tells you to fork the repository, do it.)</em>
        </li>
        <li>
          Copy and paste the entire contents (Ctrl-A + Ctrl-C) of the following textbox into the
          GitHub editor:
          <textarea
            class="form-control font-monospace d-block mb-1"
            style="height: 10rem"
            :value="displayUpdatedPosts"
          ></textarea>
        </li>
        <li>
          Click on the green "Commit changes..." button. Either keep the default message, or write
          your own (such as "Add post about my website").
        </li>
        <li>Click the green "Create pull request" button.</li>
        <li>
          Customize your request to add a post, or just click "Create pull request" to send it.
        </li>
        <li>
          The club leaders will review your post ASAP, and it will show up on the website as soon as
          it is reviewed!
        </li>
      </ol>
    </div>
  </div>
</template>
