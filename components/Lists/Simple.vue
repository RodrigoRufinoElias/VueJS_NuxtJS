<template>
  <li>{{ rotulo }}</li>
</template>

<script>
export default {
  props: {
    rotulo: {
      required: true,
      type: String
    }
  }
}
</script>
