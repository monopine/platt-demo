<template>
  <div class="markets-grid">
    <h2>Product Markets</h2>
    <div class="grid">
      <a href="#category" class="product-card">
        <div class="thumb">
          <img src="https://spaceholder.cc/200x150" alt="category image" />
        </div>
        <div class="copy">
          <p class="title">DataComm</p>
        </div>
      </a>

      <a href="#category" class="product-card">
        <div class="thumb">
          <img src="https://spaceholder.cc/200x150" alt="category image" />
        </div>
        <div class="copy">
          <p class="title">HVAC</p>
        </div>
      </a>

      <a href="#category" class="product-card">
        <div class="thumb">
          <img src="https://spaceholder.cc/200x150" alt="category image" />
        </div>
        <div class="copy">
          <p class="title">Industrial</p>
        </div>
      </a>

      <a href="#category" class="product-card">
        <div class="thumb">
          <img src="https://spaceholder.cc/200x150" alt="category image" />
        </div>
        <div class="copy">
          <p class="title">Lighting</p>
        </div>
      </a>

      <a href="#category" class="product-card">
        <div class="thumb">
          <img src="https://spaceholder.cc/200x150" alt="category image" />
        </div>
        <div class="copy">
          <p class="title">Energy Efficiency</p>
        </div>
      </a>

      <a href="#category" class="product-card">
        <div class="thumb">
          <img src="https://spaceholder.cc/200x150" alt="category image" />
        </div>
        <div class="copy">
          <p class="title">Utility</p>
        </div>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "MarketsGrid",
  data() {
    return {};
  }
};
</script>

<style lang="scss">
.markets-grid {
  display: none;
  text-align: center;

  @media (min-width: $bp-tablet) {
    display: block;
  }
}

.markets-grid .grid {
  display: flex;
  justify-content: space-between;
  margin-left: -1.6rem;
  margin-right: -1.6rem;
  width: calc(100% - 3.2);
}

.product-card {
  background: white;
  box-shadow: 1px 1px 2px 0px rgba(0, 0, 0, 0.4);
  width: 16.66%;
  margin: 0 1rem;
}

.product-card .thumb {
  height: 0;
  overflow: hidden;
  padding-top: 70%;
  position: relative;
  width: 100%;
}

.product-card .thumb img {
  object-fit: contain;
  object-position: center;
  position: absolute;
  max-width: 0;
  min-height: 100%;
  min-width: 100%;
  top: 0;
}

.product-card .copy {
  display: flex;
  flex-flow: column;
  height: 9.6rem;
  justify-content: center;
  min-height: 6rem;
  padding: 2rem 1rem 2rem;
}

.product-card .title {
  font-size: 1.8rem;
  font-weight: bold;
  margin: 0;
}
</style>
