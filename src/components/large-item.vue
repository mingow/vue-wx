<template>
  <div>
    <image class="card shadow" v-bind:style="computedClassObject" v-bind:src="src"></image>
    <p class="title" v-bind:style="style">Fashion</p>
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
.shadow {
  box-shadow: 0 0 20px #aeaeae;
}
.title {
  position: relative;
  left: 12px;
  bottom: 16px;
  font-weight: bold;
  color: #877dbb;
}
</style>
