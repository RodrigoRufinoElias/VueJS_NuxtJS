<template>
  <main>
    <h1>Home page</h1>
    <NuxtLink to="/teste/teste1">
      T1 - Test Fetch
    </NuxtLink>
    <br>
    <NuxtLink to="/teste/teste2">
      T2 - Test AsyncData
    </NuxtLink>
    <br>
    <NuxtLink to="/about">
      About (internal link that belongs to the Nuxt App)
    </NuxtLink>
    <br>
    <a href="https://nuxtjs.org">External Link to another page</a>
    <br><br>
    <div>{{ content }}</div>
    <div>I am rendered on the {{ renderedOn }} side</div>
    <br>
    <button @click="refresh">Refresh</button>
  </main>
</template>

<script lang="ts">
  import  Vue from "vue";

  export default Vue.extend({
    layout: 'sand-box',
    mounted() {
      this.$nextTick(() => {
        this.$nuxt.$loading.start()
        setTimeout(() => this.$nuxt.$loading.finish(), 500)
      })
    },
    asyncData() {
      return {
        content: 'Created at: ' + new Date(),
        renderedOn: process.client ? 'client' : 'server'
      }
    },
    methods: {
      refresh() {
        this.$nuxt.refresh()
      }
    }
  })
</script>
