<template>
  <div class="page">
    {{ About }}
    <nuxt-link to="/">Home!</nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      title: 'About',
    }
  },
}
</script>

<style>
</style>