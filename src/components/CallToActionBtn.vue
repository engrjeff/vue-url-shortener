<template>
  <button class="app-btn-cta">{{ text }}</button>
</template>

<script>
export default {
  name: "CalltoActionBtn",
  props: ["text"],
};
</script>

<style lang="scss" scoped>
/* CTA Button */
.app-btn-cta {
  /* align-self: start; */
  background-color: $primary-cyan;
  border: 0;
  border-radius: 22px;
  color: #fff;
  cursor: pointer;
  font-size: 15px;
  font-weight: 600;
  outline: none;
  padding: 12px 36px;

  &:hover {
    background-color: lighten($primary-cyan, 5%);
  }
}
</style>
