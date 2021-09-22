<template>
  <div class="url-shortener-wrap">
    <div class="url-shortener">
      <input type="text" placeholder="Shorten a link here..." v-model="url" />
      <button @click="handleShortenUrlClick">
        {{ loading ? "Shortening..." : "Shorten It!" }}
      </button>
      <p v-if="!url">Please add a link</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "UrlShortener",
  data() {
    return { url: "", shortUrl: "", loading: false };
  },
  emits: ["add-url"],
  methods: {
    async shortenUrl() {
      let linkRequest = {
        destination: this.url,
        domain: { fullName: "rebrand.ly" },
      };

      let headers = {
        "Content-Type": "application/json",
        apikey: "36a8642159b64bb781b35ddbe65cbba4",
      };

      const response = await fetch("https://api.rebrandly.com/v1/links", {
        method: "POST",
        headers,
        body: JSON.stringify(linkRequest),
      });
      const result = await response.json();
      return result;
    },
    handleShortenUrlClick() {
      if (!this.url || !this.isUrlValid) return alert("Invalid Url");

      this.loading = true;
      this.shortenUrl()
        .then((data) => {
          this.shortUrl = data.shortUrl;

          this.$emit("add-url", {
            id: data.id,
            short: data.shortUrl,
            long: this.url,
          });

          this.loading = false;
          this.url = "";
          this.shortUrl = "";
        })
        .catch(() => (this.loading = false));
    },
  },
  computed: {
    isUrlValid() {
      if (this.url === "") return false;
      try {
        new URL(this.url);
      } catch (e) {
        return false;
      }
      return true;
    },
  },
};
</script>

<style lang="scss" scoped>
.url-shortener-wrap {
  padding: 0 $container-padding;
  position: absolute;
  left: 50%;
  margin-top: -59px;
  width: 100%;

  transform: translate(-50%, 0);

  @media (min-width: 375px) and (max-width: 450px) {
    margin-top: -88px;
    padding: 0 20px;
  }

  .url-shortener {
    background-color: $primary-dark-violet;
    background-image: url(../assets/bg-shorten-desktop.svg);
    border-radius: 8px;
    padding: 40px;
    display: flex;

    @media (min-width: 375px) and (max-width: 450px) {
      background-size: cover;
      background-position-x: center;
      flex-direction: column;
      gap: 45px;
      padding: 25px;
    }

    input {
      color: $very-dark-blue;
      border: 0;
      border-radius: 5px;
      padding: 9px 16px;
      font-weight: 500;
      outline: none;
      flex: 1;
      margin-right: 20px;
      position: relative;

      @media (min-width: 375px) and (max-width: 450px) {
        margin-right: 0;
      }
    }

    p {
      color: $secondary-red;
      font-style: italic;
      font-size: 13px;
      position: absolute;
      bottom: 18px;

      @media (min-width: 375px) and (max-width: 450px) {
        bottom: 90px;
      }
    }

    button {
      justify-content: flex-start;
      background-color: $primary-cyan;
      border: 0;
      border-radius: 5px;
      color: #fff;
      cursor: pointer;
      font-weight: 600;
      outline: none;
      padding: 8px 24px;

      &:hover {
        background-color: lighten($primary-cyan, 5%);
      }

      @media (min-width: 375px) and (max-width: 450px) {
        padding: 12px 24px;
      }
    }
  }
}
</style>
