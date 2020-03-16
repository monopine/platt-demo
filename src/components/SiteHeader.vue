<template>
  <div class="site-header">
    <a class="logo" href="/">
      <img alt="Platt Logo" src="../assets/logo.png" />
    </a>
    <div class="controls">
      <button
        class="search-toggle"
        @click="
          searchVisible ? (searchVisible = false) : (searchVisible = true)
        "
      >
        <img alt="Search Icon" src="../assets/icons/white/ic_search.png" />
      </button>
      <button class="shopping-cart">
        <img
          alt="Shopping Cart Icon"
          src="../assets/icons/white/ic_shopping_cart.png"
        />
      </button>
      <button class="profile-link">
        <img alt="Profile Icon" src="../assets/icons/white/ic_person.png" />
      </button>
      <button
        class="menu-toggle"
        @click="menuVisible ? (menuVisible = false) : (menuVisible = true)"
      >
        <img alt="Menu Toggle" src="../assets/icons/white/ic_menu.png" />
      </button>
    </div>
    <SiteSearch :class="searchVisible ? ' -active' : ''" />
    <SiteMenu :class="menuVisible ? ' -active' : ''" />
  </div>
</template>

<script>
import SiteSearch from "./SiteSearch.vue";
import SiteMenu from "./SiteMenu.vue";

export default {
  name: "SiteHeader",
  data() {
    return {
      menuVisible: false,
      searchVisible: false
    };
  },
  components: { SiteSearch, SiteMenu }
};
</script>

<style scoped lang="scss">
.site-header {
  background: $header-bg;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
  padding: 1.5rem 1rem 1rem;

  @media (min-width: $bp-tablet) {
    padding-left: 2.2rem;
    padding-right: 2.2rem;
  }
}

.logo {
  width: 120px;
}

.controls {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.controls button {
  margin: 0 0.5rem;
}
</style>
