<script lang="ts">
import { defineComponent, reactive } from 'vue'
import { images } from '../utils/images'

export default defineComponent({
  setup() {
    return { images }
  },
})
</script>

<template>
  <section class="gallery">
    <div v-for="image in images" :key="image" class="gallery_item">
      <img :src="image.link" class="gallery_image" loading="lazy" />
    </div>
  </section>
</template>

<style scoped lang="scss">
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(400px, 1fr));
  grid-template-rows: repeat(3, 350px);
  grid-gap: 30px;
  width: 70%;
  margin: 1rem auto;
  animation: fadeIn 0.7s ease-in-out;
  .gallery_item {
    transition: fade;
    .gallery_image {
      border-radius: var(--radius);
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: 0.2s ease-in-out;
      &:hover {
        transform: scale(0.99);
      }
    }
    &:nth-child(2) {
      grid-column-start: 2;
      grid-column-end: 4;
    }
    &:nth-child(3) {
      grid-column-start: 1;
      grid-column-end: 3;
    }
    &:nth-child(4) {
      grid-row-start: span 2;
    }
    @media screen and (max-width: 768px) {
      &.gallery_image > * {
        grid-template-columns: repeat(1, minmax(400px, 1fr));
      }
    }
  }
}
</style>
