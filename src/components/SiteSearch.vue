<template>
  <div class="site-search">
    <form action>
      <input
        type="text"
        placeholder="What are you looking for?"
        v-model="search"
        @input="callOnChange"
      />
      <button type="submit">
        <div class="center">
          <img
            alt="Submit Search Query"
            src="../assets/icons/black/ic_search.png"
          />
        </div>
      </button>
      <ul class="search-results" v-show="isOpen">
        <li
          class="result"
          v-for="(result, i) in results"
          :key="i"
          @click="setResult(result)"
        >
          <a :href="result.url">
            <div class="thumbnail">
              <img :src="result.thumbnail" :alt="'image of' + result.name" />
            </div>
            <ul class="specifications">
              <li><span class="label">Name: </span>{{ result.name }}</li>
              <li>
                <span class="label">Birthyear: </span>{{ result.birth_year }}
              </li>
              <li>
                <span class="label">Eye-Color: </span>{{ result.eye_color }}
              </li>
              <li>
                <span class="label">Hair-Color: </span>{{ result.hair_color }}
              </li>
              <li><span class="label">Height: </span>{{ result.height }}</li>
              <li><span class="label">Mass: </span>{{ result.mass }}</li>
            </ul>
          </a>
        </li>
      </ul>
    </form>
  </div>
</template>

<script>
import _ from "lodash";

export default {
  name: "SiteSearch",
  props: {
    items: {
      type: Array,
      required: false,
      default: () => []
    }
  },
  data() {
    return {
      search: "",
      results: [],
      isOpen: false
    };
  },
  methods: {
    queryAPI(query) {
      const sanitized = query.toLowerCase();

      fetch(`https://swapi.co/api/people/?search=${sanitized}`)
        .then(response => {
          return response.json();
        })
        .then(data => {
          console.log(data.results);
          this.results = data.results.map(result => {
            return {
              thumbnail: "https://spaceholder.cc/200x166",
              url: result.url,
              name: result.name,
              birth_year: result.birth_year,
              hair_color: result.hair_color,
              eye_color: result.eye_color,
              mass: result.mass,
              height: result.height
            };
          });
        });
    },

    callOnChange: _.debounce(function() {
      if (this.search.length > 0) {
        this.onChange();
      } else {
        this.results = [];
        this.isOpen = false;
      }
    }, 1000),
    onChange() {
      this.isOpen = true;
      this.queryAPI(this.search);
    }
  }
};
</script>

<style scoped lang="scss">
.site-search {
  display: none;
  padding: 2rem 1rem 1rem;
  width: 100%;

  @media (min-width: $bp-tablet) {
    display: flex;
  }
}

.site-search.-active {
  display: flex;
}

form {
  display: flex;
  position: relative;
  width: 100%;
}

input[type="text"] {
  border-radius: 0.4rem;
  border-color: transparent;
  height: 4.6rem;
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
  background: white;
  border: 0.1rem solid $silver;
  box-shadow: 2px 3px 3px 0px rgba(0, 0, 0, 0.4);
  top: 4.6rem;
  max-height: 20rem;
  margin: 0;
  overflow: auto;
  padding: 0;
  position: absolute;
  left: 0.1rem;
  right: 0.1rem;
  z-index: 10;

  @media (min-width: $bp-tablet) {
    max-height: 60rem;
  }
}

.search-results .result a {
  border-bottom: 0.1rem solid $silver;
  cursor: pointer;
  display: flex;
  flex-flow: row wrap;
  list-style: none;
  padding: 1.4rem 1rem;
  text-align: left;

  &:hover,
  &:focus {
    background-color: $brand-primary;
    color: white;
  }

  &:last-of-type {
    border-bottom: 0;
  }
}

.search-results .result > a {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
}

.search-results .thumbnail {
  height: 6rem;
  overflow: hidden;
  position: relative;
  width: 8rem;

  @media (min-width: $bp-tablet) {
    height: 9rem;
    width: 12rem;
  }
}

.search-results .thumbnail img {
  min-height: 100%;
  min-width: 100%;
  object-fit: contain;
  object-position: center;
  position: absolute;
}

.search-results .specifications {
  align-content: center;
  display: flex;
  flex-flow: row wrap;
  justify-content: flex-start;
  list-style-type: none;
  margin: 0;
  padding: 0;
  width: calc(100% - 9rem);

  @media (min-width: $bp-tablet) {
    width: calc(100% - 14rem);
  }
}

.search-results .specifications li {
  margin: 0.25rem;

  @media (min-width: $bp-tablet) {
    font-size: 1.5rem;
    margin: 0.5rem 2rem 0.5rem;
  }
}

.search-results .label {
  font-weight: bold;
  text-transform: uppercase;
}
</style>
