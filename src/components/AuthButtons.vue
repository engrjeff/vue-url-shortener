<template>
  <div class="app-buttons flex">
    <a href="#" class="app-login-link">Login</a>
    <button class="app-btn">Sign Up</button>
  </div>
</template>

<script>
export default {
  name: "AuthButtons",
};
</script>

<style lang="scss" scoped>
.app-buttons {
  margin-left: auto;
  align-items: center;

  @media (min-width: 375px) and (max-width: 450px) {
    display: none;
  }

  .app-login-link {
    display: inline-block;
    font-weight: 500;
    margin-right: 30px;
    color: $gray;

    &:hover {
      color: $very-dark-violet;
    }
  }

  .app-btn {
    background-color: $primary-cyan;
    border: 0;
    border-radius: 18px;
    color: #fff;
    cursor: pointer;
    font-weight: 600;
    outline: none;
    padding: 8px 20px;

    &:hover {
      background-color: lighten($primary-cyan, 5%);
    }
  }
}
</style>
