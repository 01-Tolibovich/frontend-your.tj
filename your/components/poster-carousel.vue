<template>
  <div class="poster-carousel">
      <figure class="grid grid-cols-1 grid-rows-2 rounded-lg">
        <img
          class="h-full rounded-t-lg"
          src="../assets/images/cola.jpg"
          alt=""
        />
        <figcaption class="p-4 rounded-b-lg">
          <a href="/">{{ poster_carousel.link }}</a>
          <h3 class="text-black">{{ poster_carousel.title }}</h3>
          <span>{{ poster_carousel.date }}</span>
        </figcaption>
      </figure>
  </div>
</template>

<script>
export default {
  name: "poster-carousel",
  data() {
    return {
    };
  },
  props: {
    poster_carousel: {
      type: Object,
      default() {
        return {};
      },
    },
  },
};
</script>
