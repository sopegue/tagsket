<template>
  <div class="welcome relative">
    <Header
      :scroll="scroll"
      :width="width"
      class="z-50 bg-ww pb-16"
      :class="{
        shadown: scrolling > 3,
      }"
    />
    <div class="pt-16">
      <div class="w-full shadown border-b pt-2 overflow-x-auto">
        <ul
          class="nav-desc w-fit font-semibold m-0-auto flex align-center size-17 overflow-x-auto"
        >
          <li>
            <nuxt-link to="#" class="text-center current-desc">Home</nuxt-link>
          </li>
          <li>
            <nuxt-link to="#" class="text-center">Trending</nuxt-link>
          </li>
          <li>
            <nuxt-link to="#" class="text-center">Explore</nuxt-link>
          </li>
          <li>
            <nuxt-link to="#" class="text-center">Best of</nuxt-link>
          </li>
          <li>
            <nuxt-link to="#" class="text-center">Category</nuxt-link>
          </li>
        </ul>
      </div>
    </div>
    <div><nuxt-child /></div>
    <Footer />
  </div>
</template>

<script>
export default {
  data() {
    return { width: 99999, wantmax: true, show: false, scroll: 0 }
  },
  computed: {
    scrolling() {
      return this.scroll
    },
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
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.large)
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    large() {
      this.width = window.innerWidth
      if (this.wantmax === false && this.lg) this.wantmax = true
      // console.log(this.wantmax, this.lg)
    },
    handleScroll() {
      this.scroll = window.scrollY
    },
    showMenu() {
      this.$emit('showMenu', true)
    },
  },
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
