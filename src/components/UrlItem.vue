<template>
  <li>
    <p class="url-long">{{ url.long }}</p>
    <div>
      <p class="url-short">{{ url.short }}</p>
      <button @click="executeCopyUrl(url.short)" :class="{ copied: isCopied }">
        {{ isCopied ? "Copied!" : "Copy" }}
      </button>
    </div>
  </li>
</template>

<script>
export default {
  name: "UrlItem",
  props: ["url"],
  data() {
    return { isCopied: false };
  },
  methods: {
    executeCopyUrl(url) {
      navigator.clipboard.writeText(url);
      this.isCopied = true;
      setTimeout(() => (this.isCopied = false), 2000);
    },
  },
};
</script>

<style lang="scss" scoped>
li {
  background-color: #fff;
  border-radius: 5px;
  box-shadow: 0 0 20px #eee;
  display: flex;
  align-items: center;
  padding: 15px 20px;
  font-size: 13px;
  font-weight: 500;
  margin-bottom: 10px;

  @media (min-width: 375px) and (max-width: 450px) {
    flex-direction: column;
    padding: 0;

    .url-long {
      padding: 15px;
      border-bottom: 1px solid #ddd;
    }
  }

  div {
    margin-left: auto;
    display: flex;
    align-items: center;

    @media (min-width: 375px) and (max-width: 450px) {
      flex-direction: column;
      align-items: flex-start;
      padding: 15px;
      margin-left: 0;
      width: 100%;
      flex-wrap: wrap;

      p {
        padding-bottom: 15px;
        align-self: stretch;
      }

      button {
        align-self: stretch;
        width: 100% !important;
      }
    }

    p {
      color: $primary-cyan;
      font-weight: 500;
      margin-right: 20px;
    }

    button {
      align-self: start;
      background-color: $primary-cyan;
      border: 0;
      border-radius: 5px;
      color: #fff;
      cursor: pointer;
      font-weight: 600;
      outline: none;
      padding: 8px 12px;
      width: 90px;

      &:hover {
        background-color: lighten($primary-cyan, 5%);
      }

      &.copied {
        background-color: $primary-dark-violet;
      }
    }
  }
}
</style>
