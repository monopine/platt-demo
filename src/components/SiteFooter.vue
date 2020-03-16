<template>
  <div class="site-footer">
    <h2>Support Center</h2>
    <a class="h2" href="tel:800-257-5288">800-25-PLATT</a>
    <a href="tel:800-257-5288">800-257-5288</a>
    <p>
      <span class="h2">4 a.m 12 a.m. (pst)</span>
      <span class="h2">7 Days a week</span>
    </p>
    <button class="pill -gray">
      <img
        class="icon"
        src="../assets/icons/black/ic_chat.png"
        alt="chat icon"
      />Live Help
    </button>
    <ul class="footer-menu">
      <li><a href="#contact-us">Contact Us</a></li>
      <li><a href="#contact-us">What's New</a></li>
      <li><a href="#contact-us">FAQ's</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "SiteFooter",
  data() {
    return {};
  }
};
</script>

<style lang="scss">
.site-footer {
  background: $footer-bg;
  color: white;
  display: flex;
  flex-direction: column;
  font-size: 1.3rem;
  padding: 1.5rem 2rem;
  text-align: center;
}

.site-footer a {
  color: white;
}

.site-footer span {
  display: block;
}

.footer-menu {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  list-style-type: none;
  margin: auto 0 0;
  padding: 0;
}

.footer-menu li {
  margin: 1rem 1.5rem;
  font-weight: bold;
  font-size: 1.4rem;

  @media (min-width: $bp-tablet) {
    margin: 1rem 3rem;
  }
}

.footer-menu a {
  color: white;
}

.h3,
.h5 {
  color: $alto;
  font-weight: bold;
}
</style>
