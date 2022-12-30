<template>
  <div class="home-main"><img src="@/assets/StartPagePhoto.jpg" /></div>
</template>
<script setup lang="ts"></script>

<style lang="scss" scoped>
.home-main {
  max-width: 600px;
  max-height: 500px;
  position: relative;
  img {
    width: 100%;
    position: relative;
    top: 3rem;
    z-index: 1;
  }
  &::before {
    background-color: var(--color-decoration-primary);
    content: '';
    display: block;
    width: 100%;
    height: 60%;
    position: absolute;
    right: -3rem;
  }
  &::after {
    content: '';
    background-color: var(--color-decoration-secondary);
    display: block;
    width: 100%;
    height: 60%;
    position: absolute;
    bottom: -5.5rem;
    left: -3rem;
  }
}
</style>
