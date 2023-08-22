<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/vuejs/language-tools" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>

<template>
  <div class="container">
    <h1>Projects</h1>
    <div class="row row-cols-1 row-cols-md-3 g-4">
      <div class=" card p-4 gy-4" v-for="project in projects" :key="project.id">
        [{{ project.id }}] {{ project.title }}

      </div>
    </div>






    <div class="pages row justify-content-center cursor-pointer py-5">
      <div v-for="(page, index) in pages" :key="index" class="page col " :class="(page.active ? 'bg-white text-dark' : 'bg-secondary')
        + ' '
        + (page.url == null ? 'd-none' : '')" v-html="page.label" role="button" @click="loadPage(page.url)">
      </div>
    </div>
  </div>
</template>