<template>
  <div
    class="border hear-search relative flex align-center rounded"
    :class="{ 'my-shadow': focused }"
    @mouseover="
      {
        focused = true
      }
    "
    @mouseleave="manageleave"
  >
    <input
      class="w-full putput col-ws py-2 pr-8 size-16 bghover-transparent no-outline outline-none pl-3 size-14 font font-semibold color-363636"
      type="search"
      placeholder="#foryoupage, #reels, #billionaire"
      @focus="managefocus"
      @blur="manageblur"
    />
    <client-only>
      <button
        class="hover-008489 hover-bg00dce4ee btn-cere no-outline p-2 absolute right-0"
      >
        <span class="col-ws"> <i class="fas fa-search makeme-00dce4"></i></span>
      </button>
    </client-only>
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
    return {
      focused: false,
      inputfoc: false,
    }
  },
  computed: {
    scrolling() {
      return this.scroll
    },
  },
  methods: {
    manageleave() {
      if (this.inputfoc !== true) this.focused = false
    },
    managefocus() {
      this.focused = true
      this.inputfoc = true
    },
    manageblur() {
      this.focused = false
      this.inputfoc = false
    },
  },
}
</script>
