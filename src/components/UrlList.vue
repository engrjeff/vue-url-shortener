<template>
  <ul class="url-list">
    <UrlItem :key="url.id" v-for="url in urls" :url="url" />
  </ul>
</template>

<script>
import UrlItem from "./UrlItem.vue";
export default {
  components: { UrlItem },
  name: "UrlList",
  props: ["urls"],
};
</script>

<style lang="scss" scoped>
.url-list {
  padding: 10px 0;
  width: 100%;
  max-height: 300px;
  overflow-y: auto;

  @media (min-width: 375px) and (max-width: 450px) {
    margin-top: 70px;
    padding: 10px 10px;
  }
}
</style>
