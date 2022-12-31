<template>
  <div class="home-main__wrapper">
    <div class="home-main"><img src="@/assets/StartPagePhoto.jpg" /></div>
  </div>
</template>
<script setup lang="ts"></script>

<style lang="scss" scoped>
.home-main {
  align-items: center;
  display: flex;
  padding-top: 62.5%;
  margin: auto;
  position: relative;

  &__wrapper {
    // padding-top: 60%;
    // position: relative;
    height: 62.5%;
    // max-height: 206px;
    max-width: 620px;
    margin: 0 auto;
    width: 100%;
  }
  img {
    height: fit-content;
    inset: 0;
    margin: auto;
    position: absolute;
    width: 90%;
    z-index: 1;
  }
  &::before {
    background-color: var(--color-decoration-primary);
    content: '';
    display: block;
    // width: 100%;
    // height: 60%;
    position: absolute;
    // right: -3rem;
    // grid-column: 3 / 8;
    // grid-row: 1 / 4;
    right: 0;
    top: 0;
    width: 90%;
    height: 65%;
    max-width: 620px;
    max-height: 340px;
  }
  &::after {
    content: '';
    background-color: var(--color-decoration-secondary);
    display: block;
    // width: 100%;
    // height: 60%;
    position: absolute;
    // bottom: -5.5rem;
    // left: -3rem;
    /* grid-column: 1 / 5;
    grid-row: 3 / 6; */
    width: 90%;
    height: 65%;
    bottom: 0;
    left: 0;
    max-width: 620px;
    max-height: 340px;
  }
}
</style>
