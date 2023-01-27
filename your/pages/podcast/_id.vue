<template>
    <div class="limit-width single-page-padcast mt-8">
        <h1 class=" h-[400px] ">Post id: {{ $route.params.id }}</h1>
    </div>
</template>

<script>
export default {
    name: 'single-page-padcast',
    validate({params}) {
        return Boolean(params.id)
    },
    props: ['news_video_items'],
    mounted(){
        (this.$route.params.id)
    }
}
</script>