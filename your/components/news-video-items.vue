<template>
  <div class="news-video-items">
    <div class="partner-material grid grid-cols-1 grid-rows-2 rounded-lg">
      <iframe
        class=" rounded-t-xl "
        width="100%"
        height="100%"
        src="https://www.youtube.com/embed/OWcf7RN7mdQ"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen
      ></iframe>
      <article class="figcaption p-4 rounded-b-xl">
        <a href="#">{{ news_video_items.link }}</a>
        <h3 class="text-black">{{ news_video_items.title }}</h3>
        <span>{{ news_video_items.author }}</span>
      </article>
    </div>
  </div>
</template>

<script>
export default {
  name: "news-video-items",
  props: {
    news_video_items: {
      type: Object,
      default() {
        return {};
      },
    },
  },
};
</script>
