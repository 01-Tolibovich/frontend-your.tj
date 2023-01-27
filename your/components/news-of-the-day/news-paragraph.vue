<template>
  <div class="news-paragraph">
    <div>
      <p @click="goToFullPost" class="font-bold cursor-pointer">{{ news_paragraph.paragraph }}</p>
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
  methods: {
    goToFullPost() {
      this.$router.push(`/singleNews/${this.news_paragraph.id}`)
    }
  }
};
</script>
