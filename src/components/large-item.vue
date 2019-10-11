<template>
  <div>
    <image class="card" v-bind:style="computedClassObject" v-bind:src="src"></image>
    <p v-bind:style="style">demo</p>
  </div>
</template>

<script>
export default {
  props: {
    color: {
      type: String,
      default: 'blue'
    },
    imageWidth: {
      type: String,
      default: '100%'
    },
    imageHeight: {
      type: String,
      default: '100%'
    }
  },
  data () {
    return {
      imageStyle: {
        height: '100%'
      }
    }
  },
  methods: {
    showJson  (style) {
      var s = []
      for (let i in style) {
        s.push(i + ':' + style[i])
      }
      s = s.join(';')
      return s
    }
  },
  computed: {
    computedClassObject () {
      return this.showJson({
        height: Number(this.imageHeight) ? this.imageHeight + 'px' : this.imageHeight,
        width: Number(this.imageWidth) ? this.imageWidth + 'px' : this.imageWidth
      })
    }
  }
}
</script>

<style>
.card {
  padding: 10px;
}
</style>
