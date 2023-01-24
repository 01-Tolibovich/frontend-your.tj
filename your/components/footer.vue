<template>
  <div class="footer bg-black px-4 mt-28">
    <div class="limit-width-child-for-full-bg">
      <div class="grid gap-8 sm:grid-flow-col py-10 border-b border-[#9CA3AF]">
        <ul class="grid sm:grid-flow-col text-white gap-4">
          <li>
            <nuxt-link class="text-[#9CA3AF]" to="#">О проекте</nuxt-link>
          </li>
          <li>
            <nuxt-link class="text-[#9CA3AF]" to="/partners"
              >Партнерам</nuxt-link
            >
          </li>
          <li>
            <nuxt-link class="text-[#9CA3AF]" to="#"
              >Связаться с нами</nuxt-link
            >
          </li>
        </ul>
        <form action="submit" class="sm:justify-self-end">
          <input type="mail" placeholder="mail@example" />
          <button type="submit">Подписаться</button>
        </form>
      </div>
      <div class="grid grid-flow-col items-center mt-8 pb-16">
        <div>
          <p class="text-[#9CA3AF]">© 2023 Все права защищены</p>
        </div>
        <div class="grid grid-flow-col items-center gap-8 justify-end">
          <img class="w-6" src="../assets/images/facebook.svg" alt="" />
          <img class="w-6" src="../assets/images/instagram.svg" alt="" />
          <img class="w-6" src="../assets/images/twitter.svg" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "footer",
};
</script>

<style></style>
