<template>
  <header class="foodies-header">
    <div class="title">Foodies</div>
    <div class="menu">
      <span class="material-icons">menu</span>
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

  > .menu {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 43px;
    height: 35px;
    padding: 8px;

    border: 2px solid map-get($colors, "primary");
  }

  > .menu > .material-icons {
    font-size: 38px;
  }
}

/* Positioning */

/* Display & Box Model */

/* Color */

/* Text */

/* Other */
</style>
