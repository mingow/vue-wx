<template>
  <div class="grid">
    <image mode="aspectFill" class="shadow" v-bind:style="computedClassObject" v-bind:src="src"></image>
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
      default: ''
    },
    imageHeight: {
      type: String,
      default: ''
    },
    src: {
      type: String,
      dafault: ''
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
.grid {
  margin:10px;
}
.card {
  /* padding: 10px; */
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
