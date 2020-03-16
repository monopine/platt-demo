<template>
  <div class="utility-grid">
    <button class="circle">
      <div class="icon">
        <img src="../assets/icons/green/ic_line_style.png" />
      </div>
      <span class="title">Categories</span>
    </button>

    <button class="circle">
      <div class="icon">
        <img src="../assets/icons/green/ic_search.png" />
      </div>
      <span class="title">Search</span>
    </button>

    <button class="circle">
      <div class="icon">
        <img src="../assets/icons/green/ic_scanner.png" />
      </div>
      <span class="title">Scan</span>
    </button>
  </div>
</template>

<script>
export default {
  name: "UtilityGrid",
  data() {
    return {};
  }
};
</script>

<style lang="scss">
.utility-grid {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;

  @media (min-width: $bp-tablet) {
    display: none;
  }
}

.utility-grid > * {
  width: 33.33%;
}

.utility-grid .circle {
  align-content: center;
  display: flex;
  flex-flow: column;
  justify-content: center;
  text-align: center;
}

.utility-grid .icon {
  align-items: center;
  background: white;
  border-radius: 50%;
  box-shadow: 1px 1px 2px 0px #0000003d;
  display: flex;
  height: 7.5rem;
  justify-content: center;
  margin: 0 auto 1rem;
  width: 7.5rem;
}

.utility-grid .title {
  font-size: 1.5rem;
}
</style>
