<template>
  <div class="app-container">
    <header class="app-header flex">
      <h1 class="app-brand">Shortly</h1>
      <!-- navigation links -->
      <Navigation />
      <!-- navigation auth buttons -->
      <AuthButtons />
    </header>
    <main class="app-main">
      <!-- Hero Section -->
      <HeroSection />
      <!-- URL Shortner -->
      <UrlShortener @add-url="addUrl" />
      <!-- Advanced Stat Section -->
      <div class="url-list-and-stat app-section flex flex-column">
        <UrlList :urls="urls" />
        <StatSection />
      </div>
      <!-- CTA Section -->
      <CallToActionSection />
    </main>
    <!-- Footer -->
    <FooterSection />
  </div>
</template>

<script>
import AuthButtons from "./components/AuthButtons.vue";
import CallToActionSection from "./components/CallToActionSection.vue";
import FooterSection from "./components/FooterSection.vue";
import HeroSection from "./components/HeroSection.vue";
import Navigation from "./components/Navigation.vue";
import StatSection from "./components/StatSection.vue";
import UrlList from "./components/UrlList.vue";
import UrlShortener from "./components/UrlShortener.vue";

export default {
  name: "App",
  data() {
    return {
      urls: [],
    };
  },
  components: {
    Navigation,
    AuthButtons,
    HeroSection,
    StatSection,
    FooterSection,
    UrlShortener,
    CallToActionSection,
    UrlList,
  },
  mounted() {
    if (localStorage.getItem("urls"))
      this.urls = JSON.parse(localStorage.getItem("urls"));
  },
  methods: {
    addUrl(newUrl) {
      this.urls.unshift(newUrl);
      localStorage.setItem("urls", JSON.stringify(this.urls));
    },
  },
};
</script>

<style lang="scss">
/* poppins font */
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;700&display=swap");

*,
html {
  font-family: "Poppins", sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

ul {
  list-style: none;
}

a {
  text-decoration: none;
  color: inherit;
  display: inline-block;

  &:visited {
    color: inherit;
  }
}

.flex {
  display: flex;
}

.flex-column {
  flex-direction: column;
}

.app-container {
  max-width: 1440px;
  /* padding: 0 40px; */

  /* Header */
  .app-header {
    background-color: #fff;
    padding: 40px $container-padding;

    @media (min-width: 375px) and (max-width: 450px) {
      padding: 30px 20px;
    }

    .app-brand {
      color: $very-dark-violet;
      margin-right: 60px;
    }
  }

  /* Main */
  .app-main {
    .app-section {
      padding: 70px $container-padding;

      @media (min-width: 375px) and (max-width: 450px) {
        padding: 30px 10px;
      }
    }
  }

  .url-list-and-stat {
    background-color: $light-gray;
  }
}
</style>
