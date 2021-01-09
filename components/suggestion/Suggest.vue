<template>
  <div class="font-semibold">
    <nuxt-link
      to="#"
      class="button sugbtn border-0 no-outline outline-none shadow bg-white rounded-full pl-8 pr-8 flex align-center space-x-2"
    >
      <span class="color-4c4c4c size-14 suggsage relative">{{
        tag
      }}</span></nuxt-link
    >
  </div>
</template>
<script>
export default {
  props: {
    tag: {
      type: String,
      default: '',
    },
    width: {
      type: Number,
      default: 99999,
    },
  },
}
</script>
<style scoped>
img {
  width: 28px;
  height: 28px;
}
.sugbtn:hover {
  --tw-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
    0 2px 4px -1px rgba(0, 0, 0, 0.06);
  box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000),
    var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
}
</style>
