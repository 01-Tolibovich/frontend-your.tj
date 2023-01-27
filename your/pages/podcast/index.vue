<template>
  <div class="limit-width news">
    <h1 class="text-sm my-6">Подкасты</h1>
    <div class="partner-material-parrent grid md:grid-flow-col gap-4 mb-8">
      <newsVideoItems
        v-for="video in videoItems"
        :key="video.id"
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
    <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-4 mb-4">
      <fullScreenVideoItem
      v-for="item in fullScreenVideos"
      :key="item.index"
      :full_screen_video_item="item"
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
    <div class="partner-material-parrent grid md:grid-flow-col gap-4 mb-8">
      <newsVideoItems
        v-for="video in videoItems"
        :key="video.id"
        :news_video_items="video"
      />
    </div>
  </div>
</template>

<script>
import newsTitle from "../../components/news-of-the-day/news-title.vue";
import newsParagraph from "../../components/news-of-the-day/news-paragraph.vue";
import newsVideoItems from "../../components/news-video-items/index.vue";
import topNewsVideo from "../../components/top-news-video.vue";
import fullScreenVideoItem from "../../components/full-screen-video-item.vue";
export default {
  name: "IndexPage",
  components: {
    newsTitle,
    newsParagraph,
    newsVideoItems,
    topNewsVideo,
    fullScreenVideoItem
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
          id: 1,
          image: "cola.jpg",
          link: "Новости",
          title:
            "Впервые представленная в 2005 году, Coca‑Cola Без Сахара к настоящему времени стала  успешным брендом по всему миру.",
          author: "А. Гафуров К. Умедзода",
        },
        {
          id: 2,
          image: "cola.jpg",
          link: "Новости",
          title:
            "Впервые представленная в 2005 году, Coca‑Cola Без Сахара к настоящему времени стала  успешным брендом по всему миру.",
          author: "А. Гафуров К. Умедзода",
        },
        {
          id: 3,
          image: "cola.jpg",
          link: "Новости",
          title:
            "Впервые представленная в 2005 году, Coca‑Cola Без Сахара к настоящему времени стала  успешным брендом по всему миру.",
          author: "А. Гафуров К. Умедзода",
        },
      ],
      TopNewsVideo: [
        {
          id: 4,
          image: "image.jpg",
          title: "Струнами сердца. Кто он, первый таджикистанец, участник One Beat?",
          author: "А. Гафуров К. Умедзода"
        }
      ],
      fullScreenVideos: [
        {
          id: 5,
          image: "2808.jpg",
          title: "«На свет надежды нет». Почему на севере Таджикистана стали кизяк"
        },
        {
          id: 6,
          image: "2808.jpg",
          title: "«На свет надежды нет». Почему на севере Таджикистана стали кизяк"
        },
        {
          id: 7,
          image: "2808.jpg",
          title: "«На свет надежды нет». Почему на севере Таджикистана стали кизяк"
        },
        {
          id: 8,
          image: "2808.jpg",
          title: "«На свет надежды нет». Почему на севере Таджикистана стали кизяк"
        },
      ]
    };
  },
};
</script>
