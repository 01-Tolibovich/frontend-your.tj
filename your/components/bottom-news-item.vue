<template>
  <div class="bottom-news-item">
    <figure class="flex gap-4">
      <img
        class="rounded-xl"
        :src="require(`../assets/images/${bottom_news_item.image}`)"
        alt=""
      />
      <figcaption>
        <p @click="goToFullPost" class="font-bold cursor-pointer">{{ bottom_news_item.paragraph }}</p>
        <span>{{ bottom_news_item.date }}</span>
      </figcaption>
    </figure>
  </div>
</template>

<script>
export default {
  name: "bottom-news-item",
  props: {
    bottom_news_item: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  methods: {
    goToFullPost() {
      this.$router.push(`/singleNews/${this.bottom_news_item.id}`)
    }
  }
};
</script>
