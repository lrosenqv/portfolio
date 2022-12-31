<template>
  <header>
    <nav>
      <NavLinks :routes="['Home', 'About', 'Projects']" />
    </nav>
    <div class="wrapper">
      <SiteIntro msg="Louise Rosenqvist" />
    </div>
  </header>
  <main>
    <RouterView />
  </main>
  <footer>
    <a href="mailto:louise.rosenqvist@medieinstitutet.se">Email</a>
    <a href="https://www.linkedin.com/in/louise-rosenqvist-722922124/" target="_blank">Linkedin</a>
    <a href="https://github.com/lrosenqv" target="_blank">Github</a>
  </footer>
</template>

<script setup lang="ts">
import { RouterView } from 'vue-router'
import NavLinks from './components/NavLinks.vue'
import SiteIntro from './components/SiteIntro.vue'
</script>

<style lang="scss" scoped>
header {
  line-height: 1.5;
  display: flex;
  flex-direction: column;
  row-gap: 25px;
  place-content: start;
}

nav {
  column-gap: 10px;
  display: flex;
  font-size: 1.5rem;
  width: fit-content;

  @media screen and (max-width: 1024px) {
    align-self: flex-end;
    font-size: 1.4rem;
  }
}

footer {
  column-gap: 12px;
  display: flex;
  padding-bottom: 12px;
  a {
    transition: all 0.2s linear;
  }
  a::after {
    content: '';
    display: block;
    position: relative;
    transition: all 0.2s linear;
    transition-duration: 0.3s;
    width: 0;
  }
  a:hover {
    color: var(--color-text);
    &::after {
      height: 2px;
      width: 100%;
      background: var(--color-text);
      position: absolute;
    }
  }
}

@media (min-width: 1024px) {
  header {
    display: flex;
    height: 100%;
    .wrapper {
      align-items: flex-start;
    }
  }
  nav {
    text-align: left;
    font-size: 1rem;
    padding: 1rem 0;
  }
  footer a {
    font-size: 1.1rem;
    place-self: end;
  }
}
</style>
