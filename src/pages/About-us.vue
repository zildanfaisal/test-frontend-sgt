<template>
  <div class="about-page">
    <AppHeader />
    <AppSection1 />
    <AppSection2 />
    <AppEtc />
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from "../components/header.vue";
import AppSection1 from "../components/section-1.vue";
import AppSection2 from "../components/section-2.vue";
import AppEtc from "../components/etc.vue";
import AppFooter from "../components/footer.vue";

export default {
  components: { AppHeader, AppSection1, AppSection2, AppEtc, AppFooter },
};
</script>

<style scoped>
.about-page {
  width: 100%;
  margin: 0;
  padding: 0;
}
</style>
