<template>
  <main>
    <h1>T1 - Test Fetch</h1>

    <p v-if="$fetchState.pending">Loading....</p>
    <p v-else-if="$fetchState.error">Error while fetching mountains</p>

    <ul>
      <ListsSimple v-for="m of mountains" :key="m.title" :rotulo="m.title"/>
    </ul>

    <HomeLink/>
  </main>
</template>

<script lang="ts">
  import  Vue from "vue";

  export default Vue.extend({
    data() {
      return {
        mountains: []
      }
    },

    async fetch() {
      this.mountains = await this.$axios.$get('mountains');
    }
  })
</script>
