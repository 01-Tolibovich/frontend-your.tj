<template>
  <div class="news-title">
    <div class="flex flex-col h-full justify-between">
      <h2>{{ news_title.title }}</h2>
      <span>{{ news_title.time_ }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "news-title",
  props: {
    news_title: {
      type: Object,
      default() {
        return {};
      },
    },
  },
};
</script>
