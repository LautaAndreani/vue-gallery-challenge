<script lang="ts">
import { defineComponent, reactive } from 'vue'
import { dataUser } from '../types/interfaces'

export default defineComponent({
  setup() {
    const dataUser = reactive<dataUser[]>([
      { data: 100, title: 'Posts' },
      { data: 2242, title: 'Followers' },
      { data: 1432, title: 'Following' },
    ])

    return { dataUser }
  },
})
</script>

<template>
  <div class="container">
    <div v-for="post in dataUser" :key="post.data" class="container_wrapper">
      <div class="container_number">
        {{ post.data }}
      </div>
      <div class="container_info">
        {{ post.title }}
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: center;
  font-weight: 600;
  .container_wrapper {
    min-width: 6rem;
    background: var(--postsBg);
    margin: 0 0.5rem;
    padding: 20px 10px;
    border-radius: var(--radius);
    .container_number {
      color: var(--title);
    }
    .container_info {
      color: var(--postsText);
    }
  }
}
</style>
