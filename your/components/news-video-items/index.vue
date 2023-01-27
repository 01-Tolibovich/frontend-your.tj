<template>
  <div class="news-video-items">
    <figure class="grid grid-cols-1 grid-rows-2 rounded-lg">
      <div class="relative">
      <img
        class="h-full rounded-t-lg"
        :src="require(`../../assets/images/${news_video_items.image}`)"
        alt=""
      />
      <img class=" _play-button absolute top-2/4 left-1/2 w-auto h-auto cursor-pointer bg-[rgba(0,_0,_0,_0.35);] p-2 rounded-full" src="../../assets/images/play_button.svg" alt="">
      </div>
      <figcaption class="figcaption p-4 rounded-b-lg">
        <a href="/">{{ news_video_items.link }}</a>
          <h3 @click="goToFullPost" class="text-black cursor-pointer">{{ news_video_items.title }}</h3>
        <span>{{ news_video_items.author }}</span>
      </figcaption>
    </figure>
  </div>
</template>

<script>
export default {
  name: "news-video-items",
  props: ['news_video_items'],
  data() {
    return {
    }
  },
  methods: {
    goToFullPost() {
      this.$router.push(`/podcast/${this.news_video_items.id}`)
    }
  }
};
</script>

<style>

</style>