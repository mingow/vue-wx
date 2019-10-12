<template>
  <button @click="childClick" class = "base" :class="{glow:glow,solid:solid,border:!solid}">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    glow: {
      type: Boolean,
      default: false
    },
    solid: {
      type: Boolean,
      default: true
    }
  },
  methods: {
    childClick (ev) {
      this.$emit('click', ev)
    }
  }
}
</script>

<style lang="scss" scoped>
@import "static/css/theme.scss";

.context {

}
.base {
  border-radius: 20px;
  height: 40px;
  margin:20px;
  text-align: center;
  line-height: 40px;
}
.solid {
  background-color: $base-color;
  color:complement($base-color);
}
.glow {
  box-shadow: 0 0 20px $base-color;
}
.border {
  border:2px solid $base-color;
  color:$base-color;
}
</style>
