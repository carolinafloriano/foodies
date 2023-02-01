<template>
  <header class="foodies-header">
    <div class="title">Foodies</div>
    <div class="mobile-menu">
      <span class="material-icons">menu</span>
    </div>
    <div class="menu">
      <ul class="list">
        <li class="link active">Home</li>
        <li class="link">About Us</li>
        <li class="link">Service Us</li>
        <li class="link">Our Company</li>
        <li class="link">Pages</li>
      </ul>
    </div>
  </header>
</template>

<script></script>
<style lang="scss">
@import "@/assets/styles/variables.scss";

.foodies-header {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  box-sizing: border-box;
  height: 92px;
  padding: 30px;

  color: map-get($colors, "primary");
  background-color: rgb(244, 250, 255);

  > .title {
    font-size: 32px;
    font-weight: 500;
  }

  > .mobile-menu {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 43px;
    height: 35px;
    padding: 8px;

    border: 2px solid map-get($colors, "primary");
  }

  > .mobile-menu > .material-icons {
    font-size: 38px;
  }

  > .menu {
    display: none;
  }
}

@media screen and (min-width: 768px) {
  .foodies-header {
    > .mobile-menu {
      display: none;
    }

    > .menu {
      display: initial;
      padding-right: 70px;

      > .list {
        display: flex;
        flex-direction: row;
        gap: 30px;
        font-weight: 400;
        font-size: 16px;
        line-height: 19px;
        color: #1d1d1f;

        > .link {
          cursor: pointer;
        }

        > .active {
          color: map-get($colors, "primary");
        }

        > .active::after {
          content: " ";
          display: inline-block;
          width: 7px;
          height: 7px;
          border-radius: 50%;
          background: map-get($colors, "primary");
          position: relative;
          right: 50%;
          top: 15px;
        }
      }
    }
  }
}

/* Positioning */

/* Display & Box Model */

/* Color */

/* Text */

/* Other */
</style>
