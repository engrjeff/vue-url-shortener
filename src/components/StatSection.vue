<template>
  <section class="app-section section-stat flex flex-column">
    <h3>Advanced Statistics</h3>
    <p>
      Track how your links are performing across the web with our advanced
      statistics dashboard.
    </p>
    <div class="stat-cards">
      <div class="stat-line"></div>
      <Card
        icon="icon-brand-recognition.svg"
        title="Brand Recognition"
        desc="Boost your brand recognition with each click. Generic links don’t 
              mean a thing. Branded links help instil confidence in your content."
      />
      <Card
        icon="icon-detailed-records.svg"
        title="Detailed Records"
        desc="Gain insights into who is clicking your links. Knowing when and where 
              people engage with your content helps inform better decisions."
      />
      <Card
        icon="icon-fully-customizable.svg"
        title="Fully Customizable"
        desc="Improve brand awareness and content discoverability through customizable 
              links, supercharging audience engagement."
      />
    </div>
  </section>
</template>

<script>
import Card from "./Card.vue";

export default {
  components: { Card },
  name: "StatSection",
};
</script>

<style lang="scss" scoped>
.section-stat {
  align-items: center;
  background-color: $light-gray;

  h3 {
    font-size: 25px;
    color: $very-dark-violet;
    margin-top: 60px;
  }

  p {
    color: $grayish-violet;
    font-size: 13px;
    font-weight: 500;
    margin-top: 10px;
    margin-bottom: 30px;
    text-align: center;
    max-width: 30%;
  }

  @media (min-width: 375px) and (max-width: 450px) {
    h3 {
      margin-top: 20px;
    }

    p {
      max-width: 80%;
    }
  }

  .stat-cards {
    display: flex;
    gap: 30px;

    margin-top: 60px;
    position: relative;

    .stat-line {
      position: absolute;
      top: 170px;

      width: 100%;
      height: 10px;
      background-color: $primary-cyan;
    }

    .card {
      &:nth-child(3) {
        margin-top: 50px;
      }

      &:nth-child(4) {
        margin-top: 100px;
      }
    }

    @media (min-width: 375px) and (max-width: 450px) {
      flex-direction: column;

      .stat-line {
        top: 20px;
        left: 50%;
        transform: translateX(-50%);
        width: 8px;
        height: 90%;
      }
    }
  }
}
</style>
