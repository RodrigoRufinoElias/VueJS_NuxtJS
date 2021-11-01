<template>
  <main>
    <h1>T2 - Test AsyncData</h1>

    <ul>
      <li v-for="m of mountains" :key="m.title">{{ m.title }}</li>
    </ul>

    <HomeLink/>
  </main>
</template>

<script lang="ts">
  import  Vue from "vue";

  export default Vue.extend({
    async asyncData({ $axios }) {
      const mountains = await $axios.$get('mountains');
      return { mountains }
    }
  })
</script>
