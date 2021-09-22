<template>
  <section class="app-section section-hero flex">
    <!-- Hero Section - Left -->
    <div class="section-hero-left flex flex-column">
      <h1>More than just</h1>
      <h1>shorter links</h1>
      <p>
        Build your brand’s recognition and get detailed insights on how your
        links are performing.
      </p>
      <CallToActionBtn text="Get Started" />
    </div>
    <!-- Hero Section - Right -->
    <div class="section-hero-right flex flex-column">
      <img src="@/assets/illustration-working.svg" alt="illus-working" />
    </div>
  </section>
</template>

<script>
import CallToActionBtn from "./CallToActionBtn.vue";
export default {
  name: "HeroSection",
  components: {
    CallToActionBtn,
  },
};
</script>

CallToActionBtn
<style lang="scss" scoped>
.section-hero {
  background-color: #fff;
  position: relative;

  @media (min-width: 375px) and (max-width: 450px) {
    flex-direction: column;
    margin-bottom: 150px;
  }

  .section-hero-left {
    h1 {
      color: $very-dark-violet;
      font-size: 60px;
      line-height: 1.2;
    }
    p {
      color: $grayish-violet;
      font-weight: 500;
      width: 80%;

      margin-bottom: 30px;
    }

    button {
      align-self: flex-start;
    }

    @media (min-width: 375px) and (max-width: 450px) {
      order: 2;
      width: 100%;
      justify-content: center;
      align-items: center;
      text-align: center;
      margin-top: 35px;

      h1 {
        font-size: 35px;
      }

      p {
        width: 85%;
      }

      button {
        align-self: center;
      }
    }
  }

  .section-hero-right {
    @media (min-width: 375px) and (max-width: 450px) {
      order: 1;
      width: 100%;
      height: 300px;
      overflow: hidden;

      img {
        width: 100%;
        height: auto;

        @media (min-width: 375px) and (max-width: 450px) {
          height: 120%;
          width: 150%;
          transform: translateY(-50px);
        }
      }
    }
  }
}
</style>
