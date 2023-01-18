<template>
    <div class="partner-material ">
        <figure class="grid grid-cols-1 grid-rows-2 rounded-lg">
            <img class="h-full rounded-t-lg" :src="require(`../../assets/images/${partner_material.image}`)" alt="">
            <figcaption class="p-4 rounded-b-lg">
                <a href="/">{{ partner_material.link }}</a>
                <h3 class="text-black">{{ partner_material.title }}</h3>
                <span>{{ partner_material.author }}</span>
            </figcaption>
        </figure>
    </div>
</template>

<script>
export default {
    name: 'partner-material',
    props: {
        partner_material: {
            type: Object,
            default() {
                return{}
            }
        }
    }
}
</script>