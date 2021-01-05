<template>
  <div
    class="el-tab-pane"
    v-if="active"
  >
    <slot></slot>
  </div>
</template>
<script>
export default {
  props: {
    name: String
  },
  computed: {
    active () {
      return this.$parent.target === this.name
    }
  }
}
</script>