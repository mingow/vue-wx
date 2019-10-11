<template>
  <div class = "bg">
    <p class="card">
      {{text}}
    </p>
  </div>
</template>

<script>
export default {
  props: ['text']
}
</script>

<style>
.card {
  padding: 10px;
}
.bg {
  background-color: #f00;
  border-radius: 40px 50%;
}
</style>
