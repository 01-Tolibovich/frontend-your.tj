<template>
  <div class="top-news mb-8">
    <figure class="relative h-[220px] md:h-[287px] lg:h-[354px]">
        <img class="h-[220px] rounded-lg md:h-[287px] lg:h-[354px]" :src="require(`../assets/images/${top_news.image}`)" alt="">
        <figcaption class="absolute bottom-0 left-0">
            <h2 class="text-white">{{ top_news.title }}</h2>
            <span class="text-white opacity-70">{{ top_news.author }}</span>
        </figcaption>
    </figure>
  </div>
</template>

<script>
export default {
  name: "top-news",
  props: {
    top_news: {
      type: Object,
      default() {
        return {}
      }
    }
  }
};
</script>

<style>
.top-news figcaption {
    height: 100%;
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 1rem;
    background: rgb(0,0,0);
    background: linear-gradient(0deg, rgba(0,0,0,0.804359243697479) 0%, rgba(255,255,255,0) 100%);
    border-radius: 0.5rem;
}
</style>