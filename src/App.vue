<template>
  <div id="app">
    <SiteHeader />
    <div class="page-main">
      <UtilityGrid />
      <MarketsGrid />
    </div>
    <SiteFooter />
  </div>
</template>

<script>
import SiteHeader from "./components/SiteHeader.vue";
import UtilityGrid from "./components/UtilityGrid.vue";
import MarketsGrid from "./components/MarketsGrid.vue";
import SiteFooter from "./components/SiteFooter.vue";

export default {
  name: "App",
  components: {
    SiteHeader,
    UtilityGrid,
    MarketsGrid,
    SiteFooter
  }
};
</script>

<style lang="scss">
@import "./styles/_resets.scss";
@import "./styles/_buttons.scss";
@import "./styles/_typography.scss";

.page-main {
  padding: 1rem;

  @media (min-width: $bp-tablet) {
    padding: 1.6rem 2.4rem;
  }
}
</style>
