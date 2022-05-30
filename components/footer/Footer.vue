<template>
  <div class="bg-ww myfoot relative bottom-0 w-full mt-10">
    <div class="w-full px-8 foot flex align-center justify-between">
      <div class="text-center w-fit m-0-auto">
        <span class="col-ws size-12"
          >© {{ toyear }}, Xunita
          <a href="/" class="inline-block">
            <div class="h-8 relative flex align-center space-x-1">
              <h4
                class="color-white select-none size-14 font-semibold border-008489"
              >
                Tagsket
              </h4>
            </div>
          </a>
          • by Goyo</span
        >
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
  margin-top: -13px;
}
.myfoot {
  min-height: 4rem !important;
}
.headtem:hover {
  color: #00dce4 !important;
  animation: 0.2s appear;
}
@keyframes appear {
  0% {
    opacity: 0.8;
  }
}
</style>
