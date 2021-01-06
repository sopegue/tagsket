<template>
  <div class="w-full aft-head relative overflow-hidden text-center">
    <video id="myVideos" autoplay muted loop class="w-full absolute z-1">
      <source src="1.mp4" type="video/mp4" />
      Your browser does not support HTML5 video.
    </video>
  </div>
</template>
<script>
export default {
  data() {
    return { width: 99999, wantmax: true, show: false }
  },
  computed: {
    min() {
      return this.wantmax === false && this.lg < 800
    },
    lg() {
      if (this.width > 800) return true
      return false
    },
    sm() {
      if (this.width > 690) return true
      return false
    },
  },
  mounted() {
    this.large()
  },
  beforeMount() {
    window.addEventListener('resize', this.large)
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.large)
  },
  methods: {
    large() {
      this.width = window.innerWidth
      if (this.wantmax === false && this.lg) this.wantmax = true
      // console.log(this.wantmax, this.lg)
    },
    showMenu() {
      this.$emit('showMenu', true)
    },
  },
}
</script>
<style scoped>
#myVideos {
  object-position: center;
  object-fit: cover;
}
.htht {
  z-index: 9999 !important;
}
.aft-head {
  z-index: 0 !important;
  height: 512px !important;
}
</style>
