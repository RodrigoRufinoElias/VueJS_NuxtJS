<template>
  <main>
    <h1>About page with jQuery and Roboto font</h1>
    <HomeLink/>
    <br>
    <ButtonsButton rotulo="Botão" tipo="button"/>
  </main>
</template>

<script lang="ts">
  export default {
    head() {
      return {
        title: 'Sand Box - About page',
        meta: [
          {
            hid: 'about',
            name: 'about',
            content: 'About page description'
          }
        ],
        script: [
          {
            src:
              'https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.min.js'
          }
        ],
        link: [
          {
            rel: 'stylesheet',
            href: 'https://fonts.googleapis.com/css?family=Roboto&display=swap'
          }
        ]
      }
    }
  }
</script>

<style scoped>
  h1 {
    font-family: Roboto, sans-serif;
  }
</style>
