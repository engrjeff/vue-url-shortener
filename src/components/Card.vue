<template>
  <div class="card">
    <div class="card-icon">
      <img :src="require(`@/assets/${icon}`)" />
    </div>
    <h3>{{ title }}</h3>
    <p>
      {{ desc }}
    </p>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["title", "desc", "icon"],
};
</script>

<style lang="scss" scoped>
.card {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 0 20px #eee;
  padding: 80px 40px 45px 40px;
  position: relative;
  align-self: start;

  .card-icon {
    align-items: center;
    background-color: $primary-dark-violet;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    padding: 20px;
    position: absolute;
    width: 90px;
    height: 90px;
    top: -50px;
  }

  h3 {
    font-size: 24px;
    margin-bottom: 20px;
  }

  p {
    font-size: 16px;
    font-weight: 500;
    color: $grayish-violet;
  }

  @media (min-width: 375px) and (max-width: 450px) {
    text-align: center;
    margin-bottom: 10px;

    h3 {
      margin-bottom: 15px;
    }

    p {
      font-size: 15px;
    }

    .card-icon {
      left: 50%;
      transform: translateX(-50%);
    }
  }
}
</style>
