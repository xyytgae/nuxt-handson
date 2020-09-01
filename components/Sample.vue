<template>
  <div>
    <h1>{{ title }}</h1>
    Hello, {{ name }}
    <div>
      {{ reversename }}
    </div>
    <div>
      <button type="button" name="button" @click="plus">{{ num }}</button>
    </div>
    <div :class="['hide', { seven: num === 7 }]">click 7 times</div>
    <div class="slot">
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Default Title',
    },
  },
  data() {
    return {
      name: 'takanorip',
      num: 0,
    }
  },
  mounted() {
    console.log('mounted')
  },
  methods: {
    plus() {
      this.num++
    },
  },
  computed: {
    reversename() {
      return this.name
        .split('')
        .reverse()
        .join('')
    },
  },
}
</script>

<style lang="scss" scoped>
.hide {
  display: none;
  &.seven {
    display: block;
  }
}

.slot {
  color: red;
}
</style>
