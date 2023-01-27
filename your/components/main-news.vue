<template>
    <div class="main-news border-[#4176C9] border-4 rounded-xl p-4 mb-8 ">
        <h2 @click="goToFullPost" class="cursor-pointer">{{ main_news.title }}</h2>
        <span>{{ main_news.span }}</span>
    </div>
</template>

<script>
export default {
    name: "main-news",
    props: {
        main_news: {
            type: Object,
            default() {
                return {}
            }
        }
    },
    methods: {
    goToFullPost() {
      this.$router.push(`/singleNews/${this.main_news.id}`)
    }
  }
}
</script>