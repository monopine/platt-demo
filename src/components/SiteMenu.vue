<template>
  <div class="site-menu">
    <a href="#shop-all" class="primary">
      <img src="../assets/icons/black/ic_categories.png" />
      Shop All Categories
    </a>
    <a href="#my-catalogue">
      <img src="../assets/icons/black/ic_playlist_add_check.png" />
      My Catalogue
    </a>
    <a href="#my-list">
      <img src="../assets/icons/black/ic_list.png" />
      My List
    </a>
    <a href="#live-help">
      <img src="../assets/icons/green/ic_chat-active.png" />
      Live Help
    </a>
    <a href="#pim">
      <img src="../assets/icons/black/ic_check_circle.png" />
      PIM
    </a>
    <a href="#account">
      <img src="../assets/icons/black/ic_person.png" />
      Account
    </a>
    <a href="#branch-locations">
      <img src="../assets/icons/black/ic_place.png" />
      Branch Locations
    </a>
  </div>
</template>

<script>
export default {
  name: "SiteMenu",
  data() {
    return {};
  }
};
</script>

<style lang="scss" scoped>
.site-menu {
  background: white;
  display: flex;
  flex-direction: column;
  margin-bottom: -1rem;
  margin-left: -1rem;
  margin-right: -1rem;
  margin-top: 1rem;
  padding: 0 1rem;
  width: calc(100% + 2rem);

  @media (min-width: $tablet) {
    flex-direction: row;
    flex-wrap: wrap;
  }
}

.site-menu > a {
  background: url("../assets/icons/black/ic_arrow_forward.png") right 2rem
    center no-repeat;
  background-size: 1.4rem;
  border-bottom: 0.1rem solid $silver;
  font-size: 1.4rem;
  padding: 1rem 1rem 1rem 4.6rem;
  position: relative;
  width: 100%;

  @media (min-width: $tablet) {
    background-image: none;
    border-right: 0.1rem solid $silver;
    text-align: center;
    width: 33.33%;
  }

  &:last-of-type {
    border-bottom: none;

    @media (min-width: $tablet) {
      border-bottom: 0.1rem solid $silver;
    }
  }

  &:nth-of-type(1),
  &:nth-of-type(3n + 4) {
    @media (min-width: $tablet) {
      border-right-color: transparent;
    }
  }
}

.site-menu > a.primary {
  background-size: 1.5rem;
  font-weight: bold;
  font-size: 1.5rem;
  padding-bottom: 2rem;
  padding-top: 2rem;

  @media (min-width: $tablet) {
    width: 100%;
    text-align: center;
  }
}

.site-menu img {
  left: 1rem;
  position: absolute;

  @media (min-width: $tablet) {
    display: inline-block;
    margin-right: 1.5rem;
    position: relative;
    vertical-align: middle;
  }
}

.site-menu > a.primary img {
  @media (min-width: $tablet) {
    margin-top: -0.3rem;
    margin-right: 1rem;
    position: relative;
  }
}
</style>