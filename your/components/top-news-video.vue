<template>
  <div class="top-news-video">
    <div  class="relative h-[220px] md:h-[287px] lg:h-[354px] rounded-xl">
      <iframe
        class="rounded-xl"
        width="100%"
        height="100%"
        src="https://www.youtube.com/embed/OWcf7RN7mdQ"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen
      ></iframe>
      <!-- <video controls="true">
        <source src="blob:https://www.youtube.com/4e06d2e6-848f-4303-b199-2a22ae89acd4" type="video/mp4" />
    </video> -->
      <article
        :class="{ hideTextContent: toggle }"
        class="figcaption absolute bottom-0 left-0 px-4 py-4"
      >
        <h2 class="text-white">{{ top_news_video.title }}</h2>
        <span class="text-white opacity-70">{{ top_news_video.author }}</span>
      </article>
    </div>
  </div>
</template>

<script>
export default {
  name: "top-news-video",
  data() {
    return {
        toggle: false
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
