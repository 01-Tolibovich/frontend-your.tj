<template>
  <div
    class="newsletter-subscription border border-[#0048B7] rounded-xl h-full"
  >
    <form action="submit" class="grid h-full gap-4 justify-items-center p-4">
      <div class="grid grid-flow-col">
        <img
          class="self-end mb-4 w-full"
          src="../assets/images/Rectangle 34.svg"
          alt=""
          v-for="border in 12"
          :key="border"
        />
      </div>
      <h2>{{ newsletter_subscription.title }}</h2>
      <p class="font-bold text-center text-sm md:text-base lg:text-lg  ">{{ newsletter_subscription.paragraph }}</p>
      <input
        class="w-full px-4 rounded-xl border border-[#BCC1C9]"
        type="text"
        placeholder="Ваш e-mail"
      />
      <button class="w-full bg-black">ХОЧУ РАССЫЛКУ</button>
      <div class="grid grid-flow-col">
        <img
          class="mt-4 w-full"
          src="../assets/images/Rectangle 34.svg"
          alt=""
          v-for="border in 12"
          :key="border"
        />
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "newsletter-subscription",
  data() {
    return {};
  },
  props: {
    newsletter_subscription: {
      type: Object,
      default() {
        return {};
      },
    },
  },
};
</script>
