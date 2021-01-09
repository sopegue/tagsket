<template>
  <div class="mx-8 my-5 w-full shadow rounded-md d-tag">
    <div class="p-img w-full relative rounded-md">
      <a
        class="button a-tag cursor-default z-10 font-semibold vertical-center-horizontal is-lighteees no-outline outline-none shadow-md rounded-full px-8"
      >
        <span class="color-white size-16">#foryoupage</span></a
      >
      <div class="absolute bag w-full h-full"></div>
      <img class="rounded-md tag-mg" src="/tag/tiktok.jpg" alt="" />
    </div>
    <div class="aa mt-4 px-5">
      <client-only>
        <div
          class="color-4c4c4c dd-sum flex align-center justify-between size-16 font-semibold border-b-2 mb-5 pb-3"
        >
          <p class="flex align-center space-x-4 sm:space-x-6">
            <span class="flex align-center color-008489 font-semibold space-x-2"
              ><i class="far fa-eye ft size-18"></i>
              <span class="size-14">700 B</span></span
            >
            <span class="flex align-center color-008489 font-semibold space-x-2"
              ><i class="far fa-comment ft size-18"></i>
              <span class="size-14">1.900 B</span></span
            >
            <span class="flex align-center color-008489 font-semibold space-x-2"
              ><i class="far fa-heart ft size-18"></i>
              <span class="size-14">3 B</span></span
            >
            <span class="flex align-center color-008489 font-semibold space-x-2"
              ><i class="fas fa-share ft size-18"></i>
              <span class="size-14">900 M</span></span
            >
          </p>
          <div class="flex align-center space-x-4">
            <p class="color-4c4c4c used-on size-15">Used on</p>
            <p class="flex align-center space-x-2 used-img">
              <img src="/social/tiktok.png" alt="" /><img
                src="/social/fb.png"
                alt=""
              /><img src="/social/insta.png" alt="" />
            </p>
          </div></div
      ></client-only>
    </div>
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
.used-img img {
  height: 28px;
  width: 28px;
}
.p-img {
  height: 96px;
}
img {
  width: 100%;
  height: 100%;
}
.bag {
  background: rgba(0, 0, 0, 0.5);
}
.a-tag {
  display: block !important;
  width: fit-content !important;
  margin: 0 auto !important;
}
.d-tag {
  min-height: 512px;
}
.sugbtn:hover {
  --tw-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px 0 rgba(0, 0, 0, 0.06);
  box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000),
    var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
}

@media screen and (max-width: 640px) {
  .p-img {
    height: 60px;
  }
  .aa {
    padding-left: 0.5rem !important;
    padding-right: 0.5rem !important;
  }
  .dd-sum {
    flex-direction: column !important;
  }
  .a-tag {
    margin-top: -0.5rem !important;
  }
  .dd-sum > p {
    margin-bottom: 1rem !important;
  }
  .dd-sum > p span,
  .used-on {
    font-size: 14px !important;
  }
}
@media screen and (max-width: 345px) {
  .dd-sum > p span,
  .ft,
  .used-on {
    font-size: 12px !important;
  }
}
@media screen and (max-width: 300px) {
  .dd-sum > p span,
  .ft,
  .used-on {
    font-size: 10px !important;
  }
}
</style>
