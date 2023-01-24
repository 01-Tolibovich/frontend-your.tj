<template>
  <div>
    <topBanner/>
    <headerNavbar />
    <div>
      <nuxt />
    </div>
    <Footer>
      
    </Footer>
  </div>
</template>

<script>
import Footer from '../components/footer'
import topBanner from "../components/top-banner.vue";
import headerNavbar from "../components/header-navbar.vue";
import footer from "../components/footer.vue";
export default {
  name: "default",
  components: {
    Footer, headerNavbar, topBanner, footer },
};
</script>
