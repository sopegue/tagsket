<template>
  <div
    class="h-14 fixed w-full overflow-hidden text-center"
    :class="{
      'pb-5': scrolling > 455,
    }"
  >
    <div class="h-14 w-full px-8 flex align-center justify-between htht">
      <div class="w-full relative flex align-center justify-between">
        <div class="flex align-center relative">
          <a href="/" class="h-8">
            <div class="h-8 relative flex align-center space-x-2">
              <Logowhite v-if="scrolling <= 479" />
              <Logo v-else />
              <h4
                class="color-white select-none size-19 font-semibold border-b-8 border-008489"
                :class="{
                  'color-4c4c4c bb00849': scrolling > 479,
                }"
              >
                Tagsket
              </h4>
            </div>
          </a>
        </div>
        <div class="flex align-center space-x-6 cc-header">
          <nuxt-link
            to="#"
            class="color-white select-none size-14 font-semibold border-b-4 border-008489"
            :class="{
              'color-4c4c4c headarticle': scrolling > 479,
              headtem: scrolling <= 479,
            }"
            >Tik Tok</nuxt-link
          >
          <nuxt-link
            to="#"
            class="color-white select-none size-14 font-semibold border-b-4 border-008489"
            :class="{
              'color-4c4c4c headarticle': scrolling > 479,
              headtem: scrolling <= 479,
              hidden: smallx,
            }"
            >Facebook</nuxt-link
          >
          <nuxt-link
            to="#"
            class="color-white select-none size-14 font-semibold border-b-4 border-008489"
            :class="{
              'color-4c4c4c headarticle': scrolling > 479,
              headtem: scrolling <= 479,
              hidden: small,
            }"
            >Instagram</nuxt-link
          >
          <nuxt-link
            to="#"
            class="color-white select-none size-14 font-semibold border-b-4 border-008489"
            :class="{
              'color-4c4c4c headarticle': scrolling > 479,
              headtem: scrolling <= 479,
              hidden: sm,
            }"
            >Youtube</nuxt-link
          >
          <nuxt-link
            to="#"
            class="color-white select-none size-14 font-semibold border-b-4 border-008489"
            :class="{
              'color-4c4c4c headarticle': scrolling > 479,
              headtem: scrolling <= 479,
              hidden: lg,
            }"
            >Twitter</nuxt-link
          >
          <nuxt-link
            to="#"
            class="color-white select-none size-14 font-semibold border-b-4 border-008489"
            :class="{
              'color-4c4c4c headarticle': scrolling > 479,
              headtem: scrolling <= 479,
              hidden: lg,
            }"
            >Snapchat</nuxt-link
          >
        </div>
        <div class="flex align-center">
          <nuxt-link
            to="#"
            class="button rounded-full no-outline size-14 font-semibold border-0 px-6 py-2"
            :class="{
              'is-lightees': scrolling > 479,
              'is-lightes': scrolling <= 479,
            }"
            ><span
              class="color-white"
              :class="{
                'color-4c4c4c': scrolling > 479,
              }"
              >The list</span
            ></nuxt-link
          >
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    scroll: {
      type: Number,
      default: 0,
    },
    width: {
      type: Number,
      default: 99999,
    },
  },
  computed: {
    scrolling() {
      return this.scroll
    },
    lg() {
      if (this.width < 800) return true
      return false
    },
    sm() {
      if (this.width < 580) return true
      return false
    },
    small() {
      if (this.width < 500) return true
      return false
    },
    smallx() {
      if (this.width < 420) return true
      return false
    },
  },
}
</script>
<style scoped>
#myVideo {
  z-index: -5 !important;
  object-position: top;
  object-fit: scale-down;
}
.headtem:hover {
  color: #00dce4 !important;
  border-color: white !important;
  animation: 0.2s appear;
}
.hoverlist {
  background-clip: rgb(231, 230, 230) !important;
}
.headarticle,
.bb00849 {
  border-color: #008489 !important;
}
.headarticle:hover {
  border-color: #00dce4 !important;
  animation: 0.2s appear;
}
@media screen and (max-width: 640px) {
  .htht {
    padding: 0 !important;
    padding-left: 0.5rem !important;
    padding-right: 0.5rem !important;
  }
}
@keyframes appear {
  0% {
    opacity: 0.8;
  }
}
</style>
