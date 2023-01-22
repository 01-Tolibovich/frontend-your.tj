<template>
  <div>
    <topBanner/>
    <headerNavbar />
    <div>
      <nuxt />
    </div>
  </div>
</template>

<script>
import topBanner from "../components/top-banner.vue";
import headerNavbar from "../components/header-navbar.vue";
export default {
  name: "default",
  components: { headerNavbar, topBanner },
};
</script>
