<template>
  <h1>{{ slugs }}</h1>
</template>

<script>
export default {
  async asyncData({ params }) {
    const slugs = params.slugs
    return { slugs }
  },
}
</script>

<style>
</style>