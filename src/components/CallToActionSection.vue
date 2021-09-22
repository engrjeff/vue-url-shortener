<template>
  <div class="app-section section-cta flex flex-column">
    <h3>Boost your links today</h3>
    <CallToActionBtn text="Get Started" />
  </div>
</template>

<script>
import CallToActionBtn from "./CallToActionBtn.vue";
export default {
  components: { CallToActionBtn },
};
</script>

<style lang="scss" scoped>
.section-cta {
  align-items: center;
  justify-content: center;
  background-color: $primary-dark-violet;
  background-image: url("../assets/bg-boost-desktop.svg");
  background-size: contain no-repeat;

  h3 {
    color: #fff;
    font-size: 25px;
    margin-bottom: 15px;
  }

  @media (min-width: 375px) and (max-width: 450px) {
    padding: 60px 0 !important;
  }
}
</style>
