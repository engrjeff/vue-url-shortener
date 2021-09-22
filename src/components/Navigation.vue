<template>
  <nav class="app-nav flex">
    <!-- navigation links -->
    <ul class="app-nav-items flex">
      <li><a href="#">Features</a></li>
      <li><a href="#">Pricing</a></li>
      <li><a href="#">Resources</a></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "Navigation",
};
</script>

<style lang="scss" scoped>
.app-nav {
  align-items: center;

  @media (min-width: 375px) and (max-width: 450px) {
    display: none;
  }

  .app-nav-items {
    li {
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 0 10px;

      a {
        display: inline-block;
        font-weight: 500;
        color: $gray;

        &:hover {
          color: $very-dark-violet;
        }
      }
    }
  }
}
</style>
