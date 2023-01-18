<template>
  <div class="news-paragraph">
    <div>
      <p class="font-bold">{{ news_paragraph.paragraph }}</p>
      <span>{{ news_paragraph.time }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "news-paragraph",
  props: {
    news_paragraph: {
      type: Object,
      default() {
        return {};
      },
    },
  },
};
</script>
