<template>
  <footer class="view-footer">
    <div class="foodies">
      <h1 class="title">Foodies</h1>
      <p class="description">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor
      </p>
      <div class="social-icons">
        <i class="fa-brands fa-facebook"></i>
        <i class="fa-brands fa-instagram"></i>
        <i class="fa-brands fa-twitter"></i>
      </div>
    </div>
    <div class="menu">
      <h1 class="title">About Us</h1>
      <ul class="list">
        <li>About Us</li>
        <li>Service Us</li>
        <li>Contact</li>
        <li>Company</li>
      </ul>
    </div>
    <div class="menu">
      <h1 class="title">Company</h1>
      <ul class="list">
        <li>Partnership</li>
        <li>Terms of Use</li>
        <li>Privacy</li>
        <li>Sitemap</li>
      </ul>
    </div>
    <div class="contact">
      <h1 class="title">Get in Touch</h1>
      <p class="description">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor
      </p>
      <form class="subscribe">
        <input type="email" placeholder="E-mail" class="email" />
        <button type="button" class="submit">Subscribe</button>
      </form>
    </div>
    <div class="copyright">
      <p>Copyright © 2021 Foodies.</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: "VFooter",
};
</script>
<style lang="scss">
@import "@/assets/styles/variables.scss";

.view-footer {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  gap: 40px;
  margin-top: 60px;

  > .foodies {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    row-gap: 35px;
    padding: 5px 50px;

    > .title {
      font-weight: 500;
      font-size: 32px;
      line-height: 39px;
      color: map-get($colors, "primary");
    }

    > .description {
      font-weight: 400;
      font-size: 16px;
      line-height: 151.4%;
      color: #1d1d1f;
    }

    > .social-icons {
      display: flex;
      flex-direction: row;
      column-gap: 20px;
      font-size: 25px;
      color: #1d1d1f;
    }
  }

  > .menu {
    display: flex;
    flex-direction: column;
    row-gap: 25px;
    padding: 20px;

    > .title {
      font-weight: 500;
      font-size: 24px;
      line-height: 29px;
      color: #1d1d1f;
    }

    > .list {
      display: flex;
      flex-direction: column;
      row-gap: 10px;
      font-weight: 400;
      font-size: 16px;
      line-height: 19px;
      color: #1d1d1f;
    }
  }

  > .contact {
    display: flex;
    flex-direction: column;
    row-gap: 25px;
    padding: 30px;

    > .title {
      font-weight: 500;
      font-size: 24px;
      line-height: 29px;
      color: #1d1d1f;
    }

    > .description {
      font-weight: 400;
      font-size: 16px;
      line-height: 19px;

      color: #1d1d1f;
    }

    > .subscribe {
      display: flex;
      flex-direction: column;
      gap: 10px;

      > .email {
        height: 50px;
        text-align: center;
        background: #f0f1ec;
        border: 0;
        font-weight: 400;
        font-size: 14px;
        line-height: 17px;
        color: #1d1d1f;
        opacity: 0.51;
      }

      > .submit {
        background-color: map-get($colors, "primary");
        color: #ffffff;
        height: 50px;
        font-weight: 500;
        font-size: 14px;
        line-height: 17px;
        border: 0;
      }
    }
  }

  > .copyright {
    padding-bottom: 30px;
    font-weight: 400;
    font-size: 16px;
    line-height: 19px;
    color: #1d1d1f;
  }
}

@media screen and (min-width: 768px) {
  .view-footer {
    display: flex;
    flex-direction: row;
    margin-top: 0;
    text-align: left;

    > .foodies {
      align-items: baseline;
    }

    > .menu {
      flex: none;
    }

    > .contact {
      > .subscribe {
        display: flex;
        flex-direction: row;
        justify-content: space-evenly;

        > .email {
          flex: auto;
        }
        > .submit {
          flex: auto;
        }
      }
    }

    > .copyright {
      display: none;
    }
  }
}
</style>
