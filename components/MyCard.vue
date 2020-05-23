<template lang="html">
  <div class="my-card" :style="computedStyle">
    <h1 class="my-card-title">
      {{ title }}
    </h1>
    <hr />
    <div class="my-card-body">
      <slot>Default body</slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    width: {
      type: Number,
      default() {
        return null
      }
    },
    padding: {
      type: Number,
      default() {
        return null
      }
    },
    title: {
      type: String,
      default() {
        return ''
      }
    }
  },
  computed: {
    computedStyle() {
      let w = '100%'
      if (this.width) {
        w = this.width + 'px'
      }
      let p = '0 0'
      if (this.padding) {
        p = `${this.padding}px ${this.padding}px`
      }
      return { width: w, padding: p }
    }
  }
}
</script>

<style lang="css" scoped>
.my-card {
  text-align: left;
  border-radius: 2px;
  border-width: 1px;
  border-color: gray;
  border-style: solid;
}
.my-card .my-card-title {
  padding: 6px 12px;
}
.my-card .my-card-body {
  padding: 6px 12px;
}
</style>
