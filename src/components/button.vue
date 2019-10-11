<template>
  <div class = "bg">
    <p class="context">
      <slot></slot>
    </p>
  </div>
</template>

<script>
export default {
  props: ['text']
}
</script>

<style lang="scss">
@import "static/css/theme.scss";

.context {
  padding: 10px;
  text-align: center;
}
.bg {
  background-color: $base-color;
  border-radius: 20px;
  height: 40px;
}
</style>
