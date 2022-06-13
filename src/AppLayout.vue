<template>
  <AppHeader />
  <TipCard />
  <AppFooter />
</template>

<script>
import "@/assets/scss/main.scss";
import AppFooter from "./components/Footer/AppFooter.vue";
import AppHeader from "./components/Header/AppHeader.vue";
import TipCard from "./components/TipCard/TipCard.vue";

export default {
  name: "App-Layout",
  components: {
    AppFooter,
    AppHeader,
    TipCard,
  },
};
</script>
