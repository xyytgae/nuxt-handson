<template>
  <div>
    <sample :title="indexTitle">
      <div class="come">
        slot example
      </div>
    </sample>
    <nuxt-link to="/about">ABOUT</nuxt-link>
  </div>
</template>

<script>
import Sample from '~/components/Sample.vue'

export default {
  components: {
    Sample,
  },
  data() {
    return {
      indexTitle: 'Nuxt.js data',
    }
  },
}
</script>

<style></style>
