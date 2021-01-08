<template>
  <div class="bg-ww myfoot relative bottom-0 w-full mt-10">
    <div class="w-full px-8 foot flex align-center justify-between">
      <a href="/" class="h-8">
        <div class="h-8 relative flex align-center space-x-1">
          <Logowhite />
          <h4
            class="color-white select-none size-18 font-semibold border-008489"
          >
            Tagsket
          </h4>
        </div>
      </a>
      <div class="flex align-center space-x-6 cc-header">
        <nuxt-link
          to="#"
          class="color-white headtem border-b select-none size-14 font-semibold border-008489"
          >About us</nuxt-link
        >
        <nuxt-link
          to="#"
          class="color-white headtem border-b select-none size-14 font-semibold border-008489"
          >Contact us</nuxt-link
        >
      </div>
      <div>
        <span class="col-ws size-12">© {{ toyear }} by Goyo</span>
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
  },
  data() {
    return {}
  },
  computed: {
    toyear() {
      return new Date().getFullYear().toString()
    },
    scrolling() {
      return this.scroll
    },
  },
  methods: {},
}
</script>
<style scoped>
.foot {
  width: 100%;
  position: absolute;
  top: 50%;
  margin-top: -15px;
}
.myfoot {
  min-height: 5rem !important;
}
.headtem:hover {
  color: #00dce4 !important;
  animation: 0.2s appear;
}
@media screen and (max-width: 450px) {
  .foot {
    flex-direction: column !important;
    position: relative !important;
    top: 2.5rem !important;
  }
  .foot > * {
    margin-bottom: 1rem !important;
  }
  .myfoot {
    padding-bottom: 3rem !important;
  }
}
@keyframes appear {
  0% {
    opacity: 0.8;
  }
}
</style>
