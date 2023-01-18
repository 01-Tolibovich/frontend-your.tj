<template>
    <div class="main-news border-[#4176C9] border-4 rounded-xl p-4 mb-8 ">
        <h2>{{ main_news.title }}</h2>
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
    }
}
</script>