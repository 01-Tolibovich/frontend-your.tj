<template>
  <div class="full-screen-video-item">
    <figure class="relative">
      <img
        class="rounded-xl"
        :src="require(`../assets/images/${full_screen_video_item.image}`)"
        alt=""
      />
      <img
        class="_play-button absolute top-2/4 left-1/2 w-auto h-auto cursor-pointer bg-[rgba(0,_0,_0,_0.35);] p-2 rounded-full"
        src="../assets/images/play_button.svg"
        alt=""
      />
      <figcaption
        class="_overlap rounded-xl absolute bottom-0 left-0 p-4 w-full h-full flex items-end"
      >
        <h3 @click="goToFullPost" class="text-white cursor-pointer">
          {{ full_screen_video_item.title }}
        </h3>
      </figcaption>
    </figure>
  </div>
</template>

<script>
export default {
  name: "full-screen-video-item",
  props: {
    full_screen_video_item: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  methods: {
    goToFullPost() {
      this.$router.push(`/podcast/${this.full_screen_video_item.id}`);
    },
  },
};
</script>
