<script lang="ts">
import { defineComponent } from '@vue/runtime-core'
import Gallery from './components/Gallery.vue'
import Profile from './components/Profile.vue'

export default defineComponent({
  components: { Profile, Gallery },
  setup() {},
})
</script>

<template>
  <header>
    <profile />
    <gallery />
  </header>
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600&display=swap');

:root {
  --title: #4e5150;
  --subtitle: #a9a9a9;
  --postsBg: #e5e5e5;
  --postsText: #bdbdbd;
  --radius: 12px;
}

* {
  font-family: Montserrat;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  text-align: center;
}
</style>
