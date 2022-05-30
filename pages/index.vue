<template>
  <div class="welcome relative">
    <Header
      :scroll="scroll"
      :width="width"
      class="z-50 pb-16"
      :class="{
        shadown: scrolling > 535,
        'bg-ww': scrolling > 535,
      }"
    />
    <Afterheader />
    <div
      class="sticky top-0 w-full shadown border-b pt-2 overflow-x-auto"
      :class="{ 'h64 bg-white z-50': scrolling > 601 }"
    >
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
          <nuxt-link to="#" class="text-center">Social networks</nuxt-link>
        </li>
      </ul>
    </div>
    <div class="px-2 sm:px-8 mt-5">
      <h3 class="font-semibold size-19 color-gray">Social networks #tags</h3>
      <h5>Discover the #tags that are been used on social networks.</h5>
      <h3 class="font-semibold size-18 color-gray mt-5">Suggestions</h3>
    </div>
    <div
      class="flex tagsug align-center space-x-3 pt-5 pb-3 overflow-x-scroll overflow-y-hidden"
    >
      <Suggest v-for="i in 20" :key="i + 200" tag="#gegregerfyp" />
    </div>
    <div>
      <div class="px-2 sm:px-8 flex align-center flex-col">
        <Tag v-for="i in 2" :key="i" tag="#foryou" />
        <Tag v-for="i in 4" :key="i + 20" tag="#foryoupagetiktok" />
        <Tag v-for="i in 3" :key="i + 50" tag="#reels" />
      </div>
    </div>
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
      console.log(window.scrollY)
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
.h64 {
  top: 60px !important;
  animation: 0.1s appearyh;
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
