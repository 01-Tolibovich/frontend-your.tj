<template>
    <div class="partner-material ">
        <figure class="grid grid-cols-1 grid-rows-2 rounded-lg">
            <img class="h-full rounded-t-lg" :src="require(`../../assets/images/${partner_material.image}`)" alt="">
            <figcaption class="figcaption p-4 rounded-b-lg">
                <a href="/">{{ partner_material.link }}</a>
                <h3 @click="goToFullPost" class="text-black cursor-pointer">{{ partner_material.title }}</h3>
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
    },
    methods: {
    goToFullPost() {
      this.$router.push(`/singleNews/${this.partner_material.id}`)
    }
  }
}
</script>

<style>
.partner-material-parrent :nth-child(1) .figcaption {
  background-color: #000000;
  border: 2px solid #000000;
  border-top: 0;
}
.partner-material-parrent :nth-child(1) .figcaption h3 {
  color: #ffffff;
}
.partner-material-parrent :nth-child(2) .figcaption {
  background-color: #ffffff;
  border: 2px solid #cfcfcf;
  border-top: 0;
}
.partner-material-parrent :nth-child(2) .figcaption h3 {
  color: #000000;
}
.partner-material-parrent :nth-child(3) .figcaption {
  background-color: #000000;
  border: 2px solid #000000;
  border-top: 0;
}
.partner-material-parrent :nth-child(3) .figcaption h3 {
  color: #ffffff;
}
</style>