<template>
  <div class="news">
    <h1 class=" text-sm my-6 ">Подкасты</h1>
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
import newsTitle from '../components/news-of-the-day/news-title.vue';
import newsParagraph from '../components/news-of-the-day/news-paragraph.vue';
export default {
  name: "IndexPage",
  components: {newsTitle, newsParagraph,},
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
    }
  }
};
</script>
