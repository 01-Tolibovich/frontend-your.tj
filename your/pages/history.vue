<template>
  <div class="limit-width history">
    <h1 class="text-sm my-6">История</h1>
    <main>
      <topNews
        v-for="item in news_in_header"
        :key="item.index"
        :top_news="item"
      />
    </main>
    <article class="news-of-the-day_">
      <NewsTitle
        class="news-title_"
        v-for="item in newsTitle"
        :key="item.index"
        :news_title="item"
      />
      <NewsParagraph
        class="news-paragraph_"
        v-for="item in newsParagraph"
        :key="item.index"
        :news_paragraph="item"
      />
    </article>
    <div class="partner-material-parrent grid md:grid-flow-col gap-4 mb-8">
      <partnerMaterial
        v-for="item in PartnerMaterial"
        :key="item.index"
        :partner_material="item"
      />
    </div>
    <section class="overflow-x-hidden">
      <div class="mb-8">
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
    <div class="partner-material-parrent grid md:grid-flow-col gap-4 mb-8">
      <partnerMaterial
        v-for="item in PartnerMaterial"
        :key="item.index"
        :partner_material="item"
      />
    </div>
    <article class="grid md:grid-cols-2 xl:grid-cols-3 gap-x-8 gap-y-4">
      <bottomNewsItem
        v-for="item in bottom_news"
        :key="item.index"
        :bottom_news_item="item"
      />
    </article>
  </div>
</template>

<script>
import topNews from "../components/top-news.vue";
import partnerMaterial from "../components/partner-section/partner-material.vue";
import bottomNewsItem from "../components/bottom-news-item.vue";

import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";

export default {
  name: "history",
  components: {
    topNews,
    partnerMaterial,
    VueSlickCarousel,
    bottomNewsItem,
  },
  data() {
    return {
      settings: {
        arrows: false,
        dots: false,
        infinite: true,
        slidesToShow: 4,
        slidesToScroll: 1,
        arrows: true,
        autoplay: true,
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
      news_in_header: [
        {
          image: "image.jpg",
          title:
            "Струнами сердца. Кто он, первый таджикистанец, участник One Beat?",
          author: "А. Гафуров К. Умедзода",
        },
      ],
      PartnerMaterial: [
        {
          image: "cola.jpg",
          link: "Партнерский материал",
          title:
            "Впервые представленная в 2005 году, Coca‑Cola Без Сахара к настоящему времени стала  успешным брендом по всему миру.",
          author: "А. Гафуров К. Умедзода",
        },
        {
          image: "cola.jpg",
          link: "Партнерский материал",
          title:
            "Впервые представленная в 2005 году, Coca‑Cola Без Сахара к настоящему времени стала  успешным брендом по всему миру.",
          author: "А. Гафуров К. Умедзода",
        },
        {
          image: "cola.jpg",
          link: "Партнерский материал",
          title:
            "Впервые представленная в 2005 году, Coca‑Cola Без Сахара к настоящему времени стала  успешным брендом по всему миру.",
          author: "А. Гафуров К. Умедзода",
        },
      ],
      newsTitle: [
        {
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали актуальными кизяк и дрова?",
          time_: "3 часа назад",
        },
      ],
      newsParagraph: [
        {
          paragraph:
            "Цирк уехал… Как акробат из Танзании застрял в Таджикистане и уже 10 лет не может вернуться на родину",
          time: "3 часа назад",
        },
        {
          paragraph:
            "Цирк уехал… Как акробат из Танзании застрял в Таджикистане и уже 10 лет не может вернуться на родину",
          time: "3 часа назад",
        },
        {
          paragraph:
            "Цирк уехал… Как акробат из Танзании застрял в Таджикистане и уже 10 лет не может вернуться на родину",
          time: "3 часа назад",
        },
        {
          paragraph:
            "Цирк уехал… Как акробат из Танзании застрял в Таджикистане и уже 10 лет не может вернуться на родину",
          time: "3 часа назад",
        },
      ],
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
      bottom_news: [
        {
          image: "media_placeholder.jpg",
          paragraph: "Как в Турсунзаде смогли сохранить одну из самых больших школ дутара в Таджикистане",
          date: "5 дней назад"
        },
        {
          image: "media_placeholder.jpg",
          paragraph: "Как в Турсунзаде смогли сохранить одну из самых больших школ дутара в Таджикистане",
          date: "5 дней назад"
        },
        {
          image: "media_placeholder.jpg",
          paragraph: "Как в Турсунзаде смогли сохранить одну из самых больших школ дутара в Таджикистане",
          date: "5 дней назад"
        },
        {
          image: "media_placeholder.jpg",
          paragraph: "Как в Турсунзаде смогли сохранить одну из самых больших школ дутара в Таджикистане",
          date: "5 дней назад"
        },
        {
          image: "media_placeholder.jpg",
          paragraph: "Как в Турсунзаде смогли сохранить одну из самых больших школ дутара в Таджикистане",
          date: "5 дней назад"
        },
        {
          image: "media_placeholder.jpg",
          paragraph: "Как в Турсунзаде смогли сохранить одну из самых больших школ дутара в Таджикистане",
          date: "5 дней назад"
        },
      ]
    };
  },
};
</script>

<style>
.history .top-news figure {
  height: 220px;
}
.history .top-news img {
  height: 220px;
}
@media (min-width: 768px) {
  .history .top-news figure {
    height: 347px;
  }
  .history .top-news img {
    height: 347px;
  }
}
@media (min-width: 1024px) {
  .history .top-news figure {
    height: 475px;
  }
  .history .top-news img {
    height: 475px;
  }
}

.partner-material-parrent :nth-child(1) figcaption {
  background-color: #000000;
  border: 2px solid #000000;
  border-top: 0;
}
.partner-material-parrent :nth-child(1) figcaption h3 {
  color: #ffffff;
}
.partner-material-parrent :nth-child(2) figcaption {
  background-color: #ffffff;
  border: 2px solid #cfcfcf;
  border-top: 0;
}
.partner-material-parrent :nth-child(2) figcaption h3 {
  color: #000000;
}
.partner-material-parrent :nth-child(3) figcaption {
  background-color: #000000;
  border: 2px solid #000000;
  border-top: 0;
}
.partner-material-parrent :nth-child(3) figcaption h3 {
  color: #ffffff;
}
</style>
