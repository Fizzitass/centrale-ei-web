<template>
  <Banner />
  <NavBar />
  <router-view />
  <Footer />
</template>

<script>
import NavBar from "@/components/NavBar.vue";
import Footer from "@/components/Footer.vue";
import Banner from "@/components/Banner.vue";

export default {
  name: "App",
  components: {
    NavBar,
    Footer,
    Banner,
  },
};
</script>

<style scoped></style>
