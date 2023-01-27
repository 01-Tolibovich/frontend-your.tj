<template>
  <div class="index-page">
    <h1 class="limit-width text-sm my-6">Новости</h1>
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
    <section class="bg-[#F3F4F6] overflow-x-hidden ml-4">
      <div class="limit-width-child-for-full-bg">
        <div class="mt-16 mb-4 flex items-center gap-4">
          <h1>Афиша</h1>
          <nuxt-lint to="/" class="text-[#0048B7]"
            >Предложить мероприятие</nuxt-lint
          >
        </div>
        <VueSlickCarousel v-bind="settings">
          <div v-for="slide in slides" :key="slide.index">
            <figure class="grid grid-rows-2 gap-4 bg-white mb-20 mx-2">
              <img
                class="h-full rounded-t-lg"
                :src="require(`../assets/images/${slide.image}`)"
                alt=""
              />
              <figcaption class="p-4 rounded-b-lg">
                <span href="/">{{ slide.date }}</span>
                <h3 class="text-black border-b-2 border-dashed py-2 mb-2">
                  {{ slide.title }}
                </h3>
                <span class="mt-4">{{ slide.price }}</span>
                <br />
                <span>{{ slide.adress }}</span>
              </figcaption>
            </figure>
          </div>
        </VueSlickCarousel>
      </div>
    </section>
    <section class="limit-width">
      <div
        class="partner-material-parrent grid sm:grid-cols-2 lg:grid-cols-3 lg:grid-rows-2 gap-4 mt-8"
      >
        <partnerMaterial
          v-for="item in PartnerMaterial_2"
          :key="item.index"
          :partner_material="item"
        />
        <newsletterSubscription
          class="sm:col-start-1 sm:col-end-3 md:col-start-2 md:col-end-3 lg:col-start-3 lg:col-end-4"
          v-for="item in newsletterSubscription"
          :key="item.index"
          :newsletter_subscription="item"
        />
        <Advertisement
          class="sm:col-start-1 sm:col-end-3 md:col-start-1 md:col-end-2 md:row-start-2 md:row-end-3 lg:row-start-2 lg:col-start-1 lg:col-end-3"
        />
      </div>
    </section>
    <section class="bg-[#F3F4F6] overflow-x-hidden ml-4">
      <div class="limit-width-child-for-full-bg my-16">
        <div class="mt-16 mb-4 flex items-center gap-4">
          <h1>Спецпроекты</h1>
          <nuxt-lint to="/" class="text-[#0048B7]"
            >Предложить мероприятие</nuxt-lint
          >
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
    <section class="limit-width">
      <article>
        <div class="partner-material-parrent grid md:grid-flow-col gap-4 my-8">
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
        <div class="grid md:grid-cols-2 xl:grid-cols-3 gap-x-8 gap-y-4">
          <bottomNewsItem
          v-for="item in bottom_news"
          :key="item.index"
          :bottom_news_item="item"
          />
        </div>
      </article>
    </section>
  </div>
</template>

<script>
import Advertisement from "../components/advertisement";
import NewsTitle from "../components/news-of-the-day/news-title";
import MainNews from "../components/main-news";
import topNews from "../components/top-news.vue";
import mainNews from "../components/main-news.vue";
import partnerMaterial from "../components/partner-section/partner-material.vue";
import newsOfTheDay from "../components/news-of-the-day/news-title.vue";
import NewsParagraph from "../components/news-of-the-day/news-paragraph.vue";
import newsTitle from "../components/news-of-the-day/news-title.vue";
import newsletterSubscription from "../components/newsletter-subscription.vue";
import advertisement from "../components/advertisement.vue";
import bottomNewsItem from "../components/bottom-news-item.vue";

import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
export default {
  name: "IndexPage",
  components: {
    Advertisement,
    NewsTitle,
    MainNews,
    topNews,
    mainNews,
    partnerMaterial,
    newsOfTheDay,
    NewsParagraph,
    newsTitle,
    VueSlickCarousel,
    newsletterSubscription,
    advertisement,
    bottomNewsItem
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
          id: 9,
          image: "image.jpg",
          title:
            "Струнами сердца. Кто он, первый таджикистанец, участник One Beat?",
          author: "А. Гафуров К. Умедзода",
        },
        {
          id: 10,
          image: "image.jpg",
          title:
            "Струнами сердца. Кто он, первый таджикистанец, участник One Beat?",
          author: "А. Гафуров К. Умедзода",
        },
      ],
      mainNews: [
        {
          id: 11,
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали актуальными кизяк и дрова?",
          time: "Свет выключают, а денег на уголь не хватает.",
        },
      ],
      PartnerMaterial: [
        {
          id: 12,
          image: "cola.jpg",
          link: "Партнерский материал",
          title:
            "Впервые представленная в 2005 году, Coca‑Cola Без Сахара к настоящему времени стала  успешным брендом по всему миру.",
          author: "А. Гафуров К. Умедзода",
        },
        {
          id: 13,
          image: "cola.jpg",
          link: "Партнерский материал",
          title:
            "Впервые представленная в 2005 году, Coca‑Cola Без Сахара к настоящему времени стала  успешным брендом по всему миру.",
          author: "А. Гафуров К. Умедзода",
        },
        {
          id: 14,
          image: "cola.jpg",
          link: "Партнерский материал",
          title:
            "Впервые представленная в 2005 году, Coca‑Cola Без Сахара к настоящему времени стала  успешным брендом по всему миру.",
          author: "А. Гафуров К. Умедзода",
        },
      ],
      newsTitle: [
        {
          id: 15,
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали актуальными кизяк и дрова?",
          time_: "3 часа назад",
        },
      ],
      newsParagraph: [
        {
          id: 16,
          paragraph:
            "Цирк уехал… Как акробат из Танзании застрял в Таджикистане и уже 10 лет не может вернуться на родину",
          time: "3 часа назад",
        },
        {
          id: 17,
          paragraph:
            "Цирк уехал… Как акробат из Танзании застрял в Таджикистане и уже 10 лет не может вернуться на родину",
          time: "3 часа назад",
        },
        {
          id: 18,
          paragraph:
            "Цирк уехал… Как акробат из Танзании застрял в Таджикистане и уже 10 лет не может вернуться на родину",
          time: "3 часа назад",
        },
        {
          id: 19,
          paragraph:
            "Цирк уехал… Как акробат из Танзании застрял в Таджикистане и уже 10 лет не может вернуться на родину",
          time: "3 часа назад",
        },
      ],
      slides: [
        {
          id: 20,
          image: "cola.jpg",
          date: "18:00 - 12 ноября 2021, Пятница",
          title: "Фото и видео выставка синематик проекта «GRAIN»",
          price: "Бесплатно",
          adress: "Душанбе, Отель Серена",
        },
        {
          id: 21,
          image: "cola.jpg",
          date: "18:00 - 12 ноября 2021, Пятница",
          title: "Фото и видео выставка синематик проекта «GRAIN»",
          price: "Бесплатно",
          adress: "Душанбе, Отель Серена",
        },
        {
          id: 22,
          image: "cola.jpg",
          date: "18:00 - 12 ноября 2021, Пятница",
          title: "Фото и видео выставка синематик проекта «GRAIN»",
          price: "Бесплатно",
          adress: "Душанбе, Отель Серена",
        },
        {
          id: 23,
          image: "cola.jpg",
          date: "18:00 - 12 ноября 2021, Пятница",
          title: "Фото и видео выставка синематик проекта «GRAIN»",
          price: "Бесплатно",
          adress: "Душанбе, Отель Серена",
        },
        {
          id: 24,
          image: "cola.jpg",
          date: "18:00 - 12 ноября 2021, Пятница",
          title: "Фото и видео выставка синематик проекта «GRAIN»",
          price: "Бесплатно",
          adress: "Душанбе, Отель Серена",
        },
      ],
      PartnerMaterial_2: [
        {
          id: 25,
          image: "cola.jpg",
          link: "Партнерский материал",
          title:
            "Впервые представленная в 2005 году, Coca‑Cola Без Сахара к настоящему времени стала  успешным брендом по всему миру.",
          author: "А. Гафуров К. Умедзода",
        },
        {
          id: 26,
          image: "cola.jpg",
          link: "Партнерский материал",
          title:
            "Впервые представленная в 2005 году, Coca‑Cola Без Сахара к настоящему времени стала  успешным брендом по всему миру.",
          author: "А. Гафуров К. Умедзода",
        },
      ],
      newsletterSubscription: [
        {
          id: 27,
          title: "БУДЬТЕ В КУРСЕ",
          paragraph:
            "Не упустите главное - все лучшее за неделю в вашей почте!",
        },
      ],
      second_slides: [
        {
          id: 28,
          image: "2808.jpg",
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали кизяк",
        },
        {
          id: 29,
          image: "2808.jpg",
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали кизяк",
        },
        {
          id: 30,
          image: "2808.jpg",
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали кизяк",
        },
        {
          id: 31,
          image: "2808.jpg",
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали кизяк",
        },
        {
          id: 32,
          image: "2808.jpg",
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали кизяк",
        },
        {
          id: 33,
          image: "2808.jpg",
          title:
            "«На свет надежды нет». Почему на севере Таджикистана стали кизяк",
        },
      ],
      bottom_news: [
        {
          id: 34,
          image: "media_placeholder.jpg",
          paragraph: "Как в Турсунзаде смогли сохранить одну из самых больших школ дутара в Таджикистане",
          date: "5 дней назад"
        },
        {
          id: 35,
          image: "media_placeholder.jpg",
          paragraph: "Как в Турсунзаде смогли сохранить одну из самых больших школ дутара в Таджикистане",
          date: "5 дней назад"
        },
        {
          id: 36,
          image: "media_placeholder.jpg",
          paragraph: "Как в Турсунзаде смогли сохранить одну из самых больших школ дутара в Таджикистане",
          date: "5 дней назад"
        },
        {
          id: 37,
          image: "media_placeholder.jpg",
          paragraph: "Как в Турсунзаде смогли сохранить одну из самых больших школ дутара в Таджикистане",
          date: "5 дней назад"
        },
        {
          id: 38,
          image: "media_placeholder.jpg",
          paragraph: "Как в Турсунзаде смогли сохранить одну из самых больших школ дутара в Таджикистане",
          date: "5 дней назад"
        },
        {
          id: 39,
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
/* ________________________________________________ */


</style>
