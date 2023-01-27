<template>
  <div class="header-wrap">
    <header
      :class="{ open: toggle }"
      class="grid grid-cols-3 grid-rows-[repeat(2,_auto)] sm:grid-rows-1 sm:grid-cols-[repeat(3,_auto)] gap-4 items-center heared-navbar mx-auto max-w-7xl p-4"
    >
      <div @click="toggle = !toggle" class="sm:hidden w-6">
        <img
          :class="{ open: toggle }"
          class="btn-open w-6"
          src="../assets/images/menu-hamburger-svgrepo-com.svg"
          alt=""
        />
        <img
          :class="{ open: toggle }"
          class="btn-close w-7"
          src="../assets/images/close-sm-svgrepo-com.svg"
          alt=""
        />
      </div>
      <div class="logo">
        <nuxt-link to="/" class="flex justify-center sm:justify-start"
          ><img class="w-auto" src="../assets/images/logo.png" alt="logo"
        /></nuxt-link>
      </div>
      <ul
        :class="{ open: toggle }"
        class="row-start-2 row-end-3 col-start-1 col-end-4 pt-8 gap-8 sm:gap-4 sm:pt-0 sm:col-start-2 sm:col-end-3 sm:row-start-1 sm:row-end-2"
      >
        <li @click="toggle = !toggle"><nuxt-link  to="/news">Новости</nuxt-link></li>
        <li @click="toggle = !toggle"><nuxt-link  to="/history">Истории</nuxt-link></li>
        <li @click="toggle = !toggle"><nuxt-link to="/podcast">Подкасты</nuxt-link></li>
        <li @click="toggle = !toggle"><nuxt-link to="/affiche">Афиша</nuxt-link></li>
        <li @click="toggle = !toggle"><nuxt-link to="/partners">Партнерам</nuxt-link></li>
      </ul>
      <div class="search-user">
        <img
          class="hidden sm:block"
          src="../assets/images/search.svg"
          alt="search"
        />
        <nuxt-link to="/registration"
          ><img src="../assets/images/user.svg" alt="user"
        /></nuxt-link>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: "header-navbar",
  data() {
    return {
      toggle: false,
    };
  },
};
</script>

<style>
.header-wrap {
  -webkit-box-shadow: 0px 11px 7px -9px rgba(34, 60, 80, 0.2);
  -moz-box-shadow: 0px 11px 7px -9px rgba(34, 60, 80, 0.2);
  box-shadow: 0px 11px 7px -9px rgba(34, 60, 80, 0.2);
}
.heared-navbar {
  height: 55px;
  transition: 200ms ease;
}
.heared-navbar.open {
  height: 100%;
}
.heared-navbar ul {
  display: grid;
  justify-items: center;
  transform: translateX(-100%);
  opacity: 0;
  transition: 300ms ease;
}
.heared-navbar.open ul {
  transform: translateX(0);
  opacity: 1;
  transition: 300ms ease;
}
.heared-navbar ul li a {
  font-size: 1rem;
  color: black;
  font-weight: bold;
}
.heared-navbar ul li :hover {
  color: #0048b7 !important;
}
.nuxt-link-exact-active {
  color: #0048b7 !important;
}
.search-user {
  display: grid;
  grid-auto-flow: column;
  grid-template-columns: max-content;
  grid-gap: 1rem;
  justify-content: end;
}
.logo {
  width: 100%;
  top: 0;
  left: 0;
  z-index: 10;
}
.btn-open {
  display: block;
}
.btn-open.open {
  display: none;
}

.btn-close {
  display: none;
}
.btn-close.open {
  display: block;
}
@media (min-width: 640px) {
  .heared-navbar {
    height: 100%;
  }
  .heared-navbar ul {
    grid-auto-flow: column;
    z-index: 0;
    transform: translateX(0);
    opacity: 1;
    transition: 300ms ease;
  }
}
</style>
