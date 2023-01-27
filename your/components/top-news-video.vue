<template>
  <div class="top-news-video">
    <figure class="relative h-[220px] md:h-[287px] lg:h-[354px]">
      <div class="relative">
        <img
          class="h-[220px] rounded-lg md:h-[287px] lg:h-[354px]"
          :src="require(`../assets/images/${top_news_video.image}`)"
          alt=""
        />
        <img
          class="_play-button absolute top-2/4 left-1/2 w-auto h-auto cursor-pointer bg-[rgba(0,_0,_0,_0.35);] p-2 rounded-full"
          src="../assets/images/play_button.svg"
          alt=""
        />
      </div>
      <figcaption class="figcaption absolute bottom-0 left-0 p-4">
        <h2 @click="goToFullPost" class="text-white cursor-pointer">{{ top_news_video.title }}</h2>
        <span class="text-white opacity-70">{{ top_news_video.author }}</span>
      </figcaption>
    </figure>
  </div>
</template>

<script>
import VideoPlayer from "nuxt-video-player";
require("nuxt-video-player/src/assets/css/main.css");
export default {
  name: "top-news-video",
  components: { VideoPlayer },
  data() {
    return {
      toggle: false,
    };
  },
  props: {
    top_news_video: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  methods: {
    goToFullPost() {
      this.$router.push(`/podcast/${this.top_news_video.id}`)
    }
  }
};
</script>

<style>
.hideTextContent {
  display: none;
}
/* .ytp-gradient-top {
    top: auto !important;
    bottom: 0 !important;
}
.ytp-chrome-top .ytp-show-cards-title {
    top: auto !important;
    bottom: 0 !important;
} */
</style>
