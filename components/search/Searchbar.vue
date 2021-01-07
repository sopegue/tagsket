<template>
  <div class="border hear-search relative flex align-center rounded-full">
    <input
      class="w-full putput pr-12 bghover-transparent rounded-full outline-none py-2 pl-3 size-16 font font-semibold col-ws"
      type="search"
      placeholder="#foryoupage, #reels, #billionaire"
    />
    <client-only>
      <button
        class="hover-bg00dce4 btn-cer mr-2 no-outline text-center rounded-full p-2 absolute right-0"
      >
        <i class="fas fa-search col-ws"></i>
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
    return {}
  },
  computed: {
    scrolling() {
      return this.scroll
    },
  },
  methods: {},
}
</script>
