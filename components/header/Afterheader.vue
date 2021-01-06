<template>
  <div class="w-full aft-head relative overflow-hidden text-center">
    <video id="myVideos" autoplay muted loop class="w-full absolute z-1">
      <source src="1.mp4" type="video/mp4" />
      Your browser does not support HTML5 video.
    </video>
    <div style="height: 80px"></div>
    <div class="absolute w-full mt-10">
      <div class="w-full px-6 mb-10">
        <h3 class="w-full size-28 message color-white">
          Need to know what people are
          <span class="font-semibold col-00dce4">tagging</span> about ? <br />
          <span
            >Search your <span class="font-semibold col-00dce4">#tag</span> to
            find out.</span
          >
        </h3>
      </div>

      <div class="search m-0-auto"><Searchbar /></div>
    </div>
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
.search {
  width: 50%;
}
#myVideos {
  object-position: center;
  object-fit: cover;
}

.aft-head {
  z-index: 0 !important;
  height: 512px !important;
}
@media screen and (max-width: 800px) {
  .search {
    width: 70%;
  }
}
@media screen and (max-width: 450px) {
  .search {
    width: 80%;
  }
  .message {
    font-size: 20px !important;
  }
}
</style>
