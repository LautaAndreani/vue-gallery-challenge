<script lang="ts">
import { defineComponent } from 'vue'
import Cards from './Cards.vue'

export default defineComponent({
  setup() {},
  components: { Cards },
})
</script>

<template>
  <div class="container">
    <img class="container_profile" src="../assets/profile.png" alt="mi profile picture" loading="lazy" />
    <h1 class="container_text">Evan You</h1>
    <p class="container_subtitle">China</p>
    <cards />
  </div>
</template>

<style scoped lang="scss">
.container {
  padding: 20px 0;
  .container_profile {
    min-width: 10rem;
    max-width: 10rem;
    border-radius: var(--radius);
  }
  .container_text {
    font-weight: 600;
    color: var(--title);
    margin-top: 1rem;
    font-size: clamp(1.5rem, 2vw, 2rem);
  }
  .container_subtitle {
    margin-top: 0.5rem;
    font-weight: 600;
    color: var(--subtitle);
    font-size: clamp(1rem, 1vw, 1.5rem);
  }
}
</style>
