<template>
  <div class=" limit-width affiche">
    <h1 class="text-sm my-6 ">Афиша</h1>
    <section class=" overflow-x-hidden">
      <div>
        <div class=" mb-4 flex items-center gap-4">
          <h1>Актуальное</h1>
        </div>
        <VueSlickCarousel v-bind="settings">
          <div
            class="grid gap-4"
            v-for="slide in second_slides"
            :key="slide.index"
          >
            <figure class="mx-2 grid relative h-80 md:h-96">
              <img
                class="h-full rounded-lg"
                :src="require(`../assets/images/${slide.image}`)"
                alt=""
              />
              <figcaption
                class="_overlap p-4 rounded-b-lg absolute bottom-0 w-full h-full flex items-end"
              >
                <h3 class="text-white">
                  {{ slide.title }}
                </h3>
              </figcaption>
            </figure>
          </div>
        </VueSlickCarousel>
      </div>
    </section>
  </div>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
export default {
  name: "affiche",
  components: {VueSlickCarousel},
  data() {
    return {
      settings: {
        arrows: true,
        dots: false,
        infinite: true,
        slidesToShow: 4,
        slidesToScroll: 1,
        arrows: true,
        autoplay: false,
        autoplaySpeed: 2000,
        responsive: [
          {
            breakpoint: 1024,
            settings: {
              slidesToShow: 3.08,
              slidesToScroll: 1,
            },
          },
          {
            breakpoint: 768,
            settings: {
              slidesToShow: 2.07,
              slidesToScroll: 1,
            },
          },
          {
            breakpoint: 480,
            settings: {
              slidesToShow: 1.06,
              slidesToScroll: 1,
            },
          },
        ],
      },
      second_slides: [
        {
          image: "2808.jpg",
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали кизяк",
        },
        {
          image: "2808.jpg",
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали кизяк",
        },
        {
          image: "2808.jpg",
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали кизяк",
        },
        {
          image: "2808.jpg",
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали кизяк",
        },
        {
          image: "2808.jpg",
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали кизяк",
        },
        {
          image: "2808.jpg",
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали кизяк",
        },
      ],
    }
  }
};
</script>
