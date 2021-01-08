<template>
  <div
    class="h-14 fixed w-full overflow-hidden text-center"
    :class="{
      'pb-5': scrolling > 455,
    }"
  >
    <div class="h-14 w-full px-8 flex align-center justify-between htht">
      <div class="w-full relative flex align-center justify-between">
        <div
          class="flex align-center relative"
          :class="{ hidden: searching && sm640 && scroll > 262 }"
        >
          <a href="/" class="h-8">
            <div class="h-8 relative flex align-center space-x-2">
              <Logowhite />
              <h4
                class="color-white border-b-4 select-none size-19 font-semibold border-008489"
              >
                Tagsket
              </h4>
            </div>
          </a>
        </div>
        <div
          v-if="tag && searching"
          class="w-1/2 flex align-center space-x-3"
          :class="{ 'w-full': searching && sm640 }"
        >
          <client-only>
            <button
              class="hover-008489 hover-bg00dce4ee no-outline btn-search p-2"
              @click="
                {
                  opensearch = false
                }
              "
            >
              <span class="col-ws">
                <i class="fas fa-arrow-left makeme-00dce4"></i
              ></span>
            </button>
          </client-only>
          <Searchbarwhite :scroll="scroll" class="w-full" />
        </div>
        <div
          v-else-if="scrolling > 330 && searching"
          class="w-1/2 flex align-center space-x-3"
          :class="{ 'w-full': searching && sm640 }"
        >
          <client-only>
            <button
              class="hover-008489 hover-bg00dce4ee no-outline btn-search p-2"
              @click="
                {
                  opensearch = false
                }
              "
            >
              <span class="col-ws">
                <i class="fas fa-arrow-left makeme-00dce4"></i
              ></span>
            </button>
          </client-only>
          <Searchbarwhite :scroll="scroll" class="w-full" />
        </div>
        <div
          v-if="!searching"
          class="flex align-center space-x-6 cc-header"
          :class="{
            hidden: smallxx,
          }"
        >
          <nuxt-link
            to="#"
            class="color-white headtem border-b-2 select-none size-14 font-semibold border-008489"
            >Tik Tok</nuxt-link
          >
          <nuxt-link
            to="#"
            class="color-white headtem border-b-2 select-none size-14 font-semibold border-008489"
            :class="{
              hidden: smallx,
            }"
            >Facebook</nuxt-link
          >
          <nuxt-link
            to="#"
            class="color-white headtem border-b-2 select-none size-14 font-semibold border-008489"
            :class="{
              hidden: small,
            }"
            >Instagram</nuxt-link
          >
          <nuxt-link
            to="#"
            class="color-white headtem border-b-2 select-none size-14 font-semibold border-008489"
            :class="{
              hidden: sm,
            }"
            >Youtube</nuxt-link
          >
          <nuxt-link
            to="#"
            class="color-white headtem border-b-2 select-none size-14 font-semibold border-008489"
            :class="{
              hidden: lg,
            }"
            >Twitter</nuxt-link
          >
          <nuxt-link
            to="#"
            class="color-white headtem border-b-2 select-none size-14 font-semibold border-008489"
            :class="{
              hidden: lg,
            }"
            >Snapchat</nuxt-link
          >
        </div>
        <div
          v-if="tag"
          class="flex align-center space-x-5"
          :class="{ hidden: searching && sm640 }"
        >
          <div v-show="!searching">
            <client-only>
              <button
                class="no-outline p-2 hover-bg00dce4ee"
                @click="
                  {
                    opensearch = true
                  }
                "
              >
                <span class="col-ws">
                  <i class="fas fa-search size-18 makeme-00dce4"></i
                ></span>
              </button>
            </client-only>
          </div>
          <nuxt-link
            to="#"
            class="button rounded-full is-lightees no-outline size-14 font-semibold border-0 px-6 py-2"
            ><span class="color-white">Explore</span></nuxt-link
          >
        </div>
        <div
          v-else
          class="flex align-center space-x-5"
          :class="{ hidden: searching && sm640 && scroll > 262 }"
        >
          <div v-show="scrolling > 330 && !searching">
            <client-only>
              <button
                class="no-outline p-2 hover-bg00dce4ee"
                @click="
                  {
                    opensearch = true
                  }
                "
              >
                <span class="col-ws">
                  <i class="fas fa-search size-18 makeme-00dce4"></i
                ></span>
              </button>
            </client-only>
          </div>
          <nuxt-link
            to="#"
            class="button rounded-full is-lightees no-outline size-14 font-semibold border-0 px-6 py-2"
            ><span class="color-white">Explore</span></nuxt-link
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
  data() {
    return { opensearch: false }
  },
  computed: {
    tag() {
      return this.$route.path.includes('/tag')
    },
    searching() {
      return this.opensearch === true
    },
    scrolling() {
      return this.scroll
    },
    lg() {
      if (this.width < 810) return true
      return false
    },
    sm640() {
      if (this.width < 640) return true
      return false
    },
    sm() {
      if (this.width < 670) return true
      return false
    },
    small() {
      if (this.width < 548) return true
      return false
    },
    smallx() {
      if (this.width < 460) return true
      return false
    },
    smallxx() {
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
