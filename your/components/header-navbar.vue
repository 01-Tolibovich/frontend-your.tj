<template>
  <div class="header-wrap ">
    <header class="heared-navbar mx-auto max-w-7xl p-4">
      <div class="logo"><nuxt-link to="/"><img class="w-auto" src="../assets/images/logo.png" alt="logo" /></nuxt-link></div>
      <ul>
        <li><nuxt-link to="/">Новости</nuxt-link></li>
        <li><nuxt-link to="/history">Истории</nuxt-link></li>
        <li><nuxt-link to="/podcast">Подкасты</nuxt-link></li>
        <li><nuxt-link to="/affiche">Афиша</nuxt-link></li>
        <li><nuxt-link to="/partners">Партнерам</nuxt-link></li>
      </ul>
      <div class="search-user">
        <img src="../assets/images/search.svg" alt="search" />
        <nuxt-link to="/registration"><img src="../assets/images/user.svg" alt="user" /></nuxt-link>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: "header-navbar",
};
</script>

<style>
.header-wrap {
  -webkit-box-shadow: 0px 11px 7px -9px rgba(34, 60, 80, 0.2);
  -moz-box-shadow: 0px 11px 7px -9px rgba(34, 60, 80, 0.2);
  box-shadow: 0px 11px 7px -9px rgba(34, 60, 80, 0.2);
}
.heared-navbar {
  display: grid;
  grid-auto-flow: column;
  grid-gap: 1rem;
}
.heared-navbar ul {
  display: grid;
  grid-auto-flow: column;
  justify-items: center;
  grid-gap: 1rem;
}
.heared-navbar ul li a {
  font-size: 1rem;
  color: black;
  font-weight: bold;
}
.heared-navbar ul li :hover{
  color: #0048B7 !important;
}
.nuxt-link-exact-active {
  color: #0048B7 !important;
}
.search-user {
  display: grid;
  grid-auto-flow: column;
  grid-template-columns: max-content;
  grid-gap: 1rem;
  justify-content: end;
}
@media (max-width: 450px) {
  .header-wrap ul {
    display: none;
  }
}
</style>
