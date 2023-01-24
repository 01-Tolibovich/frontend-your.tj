<template>
  <div class="limit-width news">
    <h1 class="text-sm my-6">Подкасты</h1>
    <div class="partner-material-parrent grid md:grid-flow-col gap-4 mb-8">
      <newsVideoItems
        v-for="video in videoItems"
        :key="video.index"
        :news_video_items="video"
      />
    </div>
    <div class="topNews mb-8">
      <topNewsVideo
      v-for="video in TopNewsVideo"
      :key="video.index"
      :top_news_video="video"
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
    
  </div>
</template>

<script>
import newsTitle from "../components/news-of-the-day/news-title.vue";
import newsParagraph from "../components/news-of-the-day/news-paragraph.vue";
import newsVideoItems from "../components/news-video-items.vue";
import topNewsVideo from "../components/top-news-video.vue";
export default {
  name: "IndexPage",
  components: {
    newsTitle,
    newsParagraph,
    newsVideoItems,
    topNewsVideo
  },
  data() {
    return {
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
      videoItems: [
        {
          link: "Новости",
          title:
            "Впервые представленная в 2005 году, Coca‑Cola Без Сахара к настоящему времени стала  успешным брендом по всему миру.",
          author: "А. Гафуров К. Умедзода",
        },
        {
          link: "Новости",
          title:
            "Впервые представленная в 2005 году, Coca‑Cola Без Сахара к настоящему времени стала  успешным брендом по всему миру.",
          author: "А. Гафуров К. Умедзода",
        },
        {
          link: "Новости",
          title:
            "Впервые представленная в 2005 году, Coca‑Cola Без Сахара к настоящему времени стала  успешным брендом по всему миру.",
          author: "А. Гафуров К. Умедзода",
        },
      ],
      TopNewsVideo: [
        {
          title: "Струнами сердца. Кто он, первый таджикистанец, участник One Beat?",
          author: "А. Гафуров К. Умедзода"
        }
      ]
    };
  },
};
</script>
