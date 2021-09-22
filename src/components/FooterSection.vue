<template>
  <footer class="app-footer">
    <div class="flex">
      <h3>Shortly</h3>
      <div class="footer-links">
        <!-- Features -->
        <ul>
          <li class="title">Features</li>
          <li><a href="#">Link Shortening</a></li>
          <li><a href="#">Branded Links</a></li>
          <li><a href="#">Analytics</a></li>
        </ul>
        <!-- Resources -->
        <ul>
          <li class="title">Resources</li>
          <li><a href="#">Blog</a></li>
          <li><a href="#">Developers</a></li>
          <li><a href="#">Support</a></li>
        </ul>

        <!-- Company -->
        <ul>
          <li class="title">Company</li>
          <li><a href="#">About</a></li>
          <li><a href="#">Our Team</a></li>
          <li><a href="#">Careers</a></li>
          <li><a href="#">Contact</a></li>
        </ul>

        <!-- Social -->
        <ul class="social-links">
          <li>
            <a href="#"><img src="@/assets/icon-facebook.svg" /></a>
          </li>
          <li>
            <a href="#"><img src="@/assets/icon-twitter.svg" /></a>
          </li>
          <li>
            <a href="#"><img src="@/assets/icon-pinterest.svg" /></a>
          </li>
          <li>
            <a href="#"><img src="@/assets/icon-instagram.svg" /></a>
          </li>
        </ul>
      </div>
    </div>
    <div class="attribution">
      Challenge by
      <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
        >&nbsp;Frontend Mentor</a
      >. Coded by <a href="#">&nbsp;Jeffrey Segovia</a>.
    </div>
  </footer>
</template>

<script>
export default {
  name: "FooterSection",
};
</script>

<style lang="scss" scoped>
.app-footer {
  background-color: $very-dark-violet;
  color: #fff;
  padding: $container-padding;

  h3 {
    font-size: 23px;
  }

  .footer-links {
    margin-left: auto;

    display: flex;
    font-size: 13px;

    ul {
      margin-right: 60px;

      .title {
        color: #fff;
        font-size: 14px;
        font-weight: 500;
        margin-bottom: 15px;
      }

      li {
        color: $gray;

        a {
          padding: 4px 0;

          &:hover {
            color: $primary-cyan;
          }
        }
      }
    }

    .social-links {
      display: flex;

      li {
        margin: 0 5px;
      }

      img {
        width: 18px;
        height: auto;
      }
    }
  }

  /* attribution */
  .attribution {
    color: $gray;
    font-size: 13px;
    display: flex;
    justify-content: center;
    padding-top: 60px;

    a {
      color: $primary-cyan;
    }
  }

  @media (min-width: 375px) and (max-width: 450px) {
    div {
      h3 {
        margin-bottom: 40px;
      }
      flex-direction: column;
      align-items: center;
    }

    .footer-links {
      margin-left: 0;
      text-align: center;
      ul {
        margin: 20px 0;
      }
    }
  }
}
</style>
