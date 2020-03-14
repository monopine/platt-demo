<template>
  <div class="site-search">
    <form action>
      <input type="text" placeholder="What are you looking for?" v-model="search" @input="onChange" />
      <button type="submit">
        <div class="center">
          <img alt="Submit Search Query" src="../assets/icons/black/ic_search.png" />
        </div>
      </button>
      <ul class="search-results">
        <li class="search-result"></li>
      </ul>
    </form>
  </div>
</template>

<script>
export default {
  name: "SiteSearch",
  data() {
    return {
      search: ""
    };
  },
  methods: {
    onChange() {
      //
    }
  }
};
</script>

<style scoped lang="scss">
.site-search {
  padding: 2rem 1rem 1rem;
  width: 100%;
}

form {
  display: flex;
  position: relative;
  width: 100%;
}

input[type="text"] {
  border-radius: 0.4rem;
  border-color: transparent;
  padding: 1.25rem 4.2rem 1.25rem 0.5rem;
  width: 100%;

  &:focus {
    border-color: $brand-light;
    box-shadow: 0 0 0 1px $brand-light;
    outline: 2px solid transparent;
  }
}

button[type="submit"] {
  align-content: center;
  align-items: stretch;
  background: white;
  border-bottom-right-radius: 0.4rem;
  border-top-right-radius: 0.4rem;
  border: 0.2rem solid transparent;
  display: flex;
  justify-content: center;
  width: 4.2rem;
  position: absolute;
  top: 0.2rem;
  bottom: 0.2rem;
  right: 0.2rem;
}

button[type="submit"] img {
  height: 1.8rem;
  width: 1.8rem;
}

.center {
  align-self: center;
}

.search-results {
  border: 0.1rem solid $silver;
  height: 10rem;
  margin: 0;
  overflow: auto;
  padding: 0;
}

.search-results .result {
  cursor: pointer;
  list-style: none;
  padding: 0.4rem 0.2rem;
  text-align: left;

  &:hover,
  &:focus {
    background-color: $brand-primary;
    color: white;
  }
}
</style>