<template>
  <div class="index-page">
    <h1 class=" limit-width text-sm my-6 ">Новости</h1>
    <section class="limit-width">
      <article>
        <div class="topNews">
          <topNews
            v-for="item in news_in_header"
            :key="item.index"
            :top_news="item"
          />
        </div>
        <div>
          <MainNews
            v-for="item in mainNews"
            :key="item.index"
            :main_news="item"
          />
        </div>
        <div class="partner-material-parrent grid md:grid-flow-col gap-4 mb-8">
          <partnerMaterial
            v-for="item in PartnerMaterial"
            :key="item.index"
            :partner_material="item"
          />
        </div>
        <div class="news-of-the-day_">
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
        </div>
      </article>
    </section>
    <section class=" bg-[#F3F4F6] overflow-x-hidden ml-4">
      <div class="limit-width-child-for-full-bg">
        <div class="mt-6 mb-4 flex">
          <h1>Афиша</h1>
          <nuxt-lint to="/">Предложить мероприятие</nuxt-lint>
        </div>
        <VueSlickCarousel v-bind="settings">
          <div v-for="slide in slides" :key="slide.index">
            <figure class="grid grid-rows-2 gap-4 bg-white  mb-20 mx-4">
              <img
                class="h-full rounded-t-lg"
                :src="require(`../assets/images/${slide.image}`)"
                alt=""
              />
              <figcaption class="p-4 rounded-b-lg">
                <span href="/">{{ slide.date }}</span>
                <h3 class="text-black border-b-2 border-dashed py-2 mb-2">{{ slide.title }}</h3>
                <span class="mt-4">{{ slide.price }}</span>
                <br>
                <span>{{ slide.adress }}</span>
              </figcaption>
            </figure>
          </div>
        </VueSlickCarousel>
      </div>
    </section>
  </div>
</template>

<script>
import NewsTitle from "../components/news-of-the-day/news-title";
import MainNews from "../components/main-news";
import topNews from "../components/top-news.vue";
import mainNews from "../components/main-news.vue";
import partnerMaterial from "../components/partner-section/partner-material.vue";
import newsOfTheDay from "../components/news-of-the-day/news-title.vue";
import NewsParagraph from "../components/news-of-the-day/news-paragraph.vue";
import newsTitle from "../components/news-of-the-day/news-title.vue";

import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
export default {
  name: "IndexPage",
  components: {
    NewsTitle,
    MainNews,
    topNews,
    mainNews,
    partnerMaterial,
    newsOfTheDay,
    NewsParagraph,
    newsTitle,
    VueSlickCarousel,
  },
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
      news_in_header: [
        {
          image: "image.jpg",
          title:
            "Струнами сердца. Кто он, первый таджикистанец, участник One Beat?",
          author: "А. Гафуров К. Умедзода",
        },
        {
          image: "image.jpg",
          title:
            "Струнами сердца. Кто он, первый таджикистанец, участник One Beat?",
          author: "А. Гафуров К. Умедзода",
        },
      ],
      mainNews: [
        {
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали актуальными кизяк и дрова?",
          time: "Свет выключают, а денег на уголь не хватает.",
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
      slides: [
        {
          image: "cola.jpg",
          date: "18:00 - 12 ноября 2021, Пятница",
          title: "Фото и видео выставка синематик проекта «GRAIN»",
          price: "Бесплатно",
          adress: "Душанбе, Отель Серена",
        },
        {
          image: "cola.jpg",
          date: "18:00 - 12 ноября 2021, Пятница",
          title: "Фото и видео выставка синематик проекта «GRAIN»",
          price: "Бесплатно",
          adress: "Душанбе, Отель Серена",
        },
        {
          image: "cola.jpg",
          date: "18:00 - 12 ноября 2021, Пятница",
          title: "Фото и видео выставка синематик проекта «GRAIN»",
          price: "Бесплатно",
          adress: "Душанбе, Отель Серена",
        },
        {
          image: "cola.jpg",
          date: "18:00 - 12 ноября 2021, Пятница",
          title: "Фото и видео выставка синематик проекта «GRAIN»",
          price: "Бесплатно",
          adress: "Душанбе, Отель Серена",
        },
        {
          image: "cola.jpg",
          date: "18:00 - 12 ноября 2021, Пятница",
          title: "Фото и видео выставка синематик проекта «GRAIN»",
          price: "Бесплатно",
          adress: "Душанбе, Отель Серена",
        },
      ],
    };
  },
};
</script>

<style>
.topNews {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1rem;
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
/* ________________________________________________ */
</style>
