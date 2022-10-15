<template>
  <main class="main">
    <the-hero />

    <the-secondary />
  </main>
</template>

<script>
import TheHero from '../components/TheHero.vue'
import TheSecondary from '../components/TheSecondary.vue'

export default {
  components: {
    TheHero,
    TheSecondary
  }
}
</script>

<style>


</style>
