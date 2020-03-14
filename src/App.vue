<template>
  <div id="app">
    <SiteHeader />
    <p>
      Looking for good structure, solid CSS layout, not looking for CSS
      frameworks (like Bootstrap, Bulma, etc.) would like to see custom media
      queries. They can use a JavaScript framework though (like Angular, Vue,
      etc).
    </p>
    <p>So, the three main points are:</p>
    <ul>
      <li>
        Make an ‘autocomplete’ of sorts in the main search bar using any api:
        (https://swapi.co/documentation,https://dog.ceo/dog-api/, etc). Can be
        done in any JavaScript framework you want to use.
      </li>
      <li>Do not use a CSS framework (Bootstrap, Bulma, etc.)</li>
      <li>Make sure the application is buildable</li>
    </ul>
  </div>
</template>

<script>
import SiteHeader from "./components/SiteHeader.vue";

export default {
  name: "App",
  components: {
    SiteHeader
  }
};
</script>

<style lang="scss">
@import "./styles/_resets.scss";
</style>
