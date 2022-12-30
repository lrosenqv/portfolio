<template>
  <header>
    <div class="wrapper">
      <nav>
        <div class="link-border"><RouterLink to="/">Home</RouterLink></div>
        <div class="link-border">
          <RouterLink to="/about">About</RouterLink>
        </div>
        <div class="link-border">
          <RouterLink to="/projects">Projects</RouterLink>
        </div>
      </nav>
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
import { RouterLink, RouterView } from 'vue-router'
import SiteIntro from './components/SiteIntro.vue'
</script>

<style lang="scss" scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  column-gap: 1rem;
  display: flex;
  font-size: 12px;
  text-align: center;
  width: 100%;
}

nav a.router-link-exact-active {
  color: var(--vt-c-lilac);
}

nav a {
  color: var(--color-heading);
  display: inline-block;
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem;
  padding: 0 0.8rem;
}
nav a {
  border-top: 0px;
  display: block;
  background: var(--color-background);
  position: relative;
  z-index: 2;
  &::before,
  &::after {
    content: '';
    width: 2px;
    height: 0;
    position: absolute;
    transition: all 0.2s linear;
  }
  &:hover::before,
  &:hover::after {
    width: 100%;
    height: 100%;
    border: 2px solid var(--color-text);
    z-index: 1;
  }
}
.link-border {
  height: fit-content;
  width: fit-content;
  position: relative;
  background: none;
  // background: var(--color-text);

  &::before,
  &::after {
    content: '';
    width: 0;
    height: 2px;
    position: absolute;
    transition: all 0.2s linear;
  }

  &::after {
    right: 0;
    bottom: 0;
    border-right: 2px solid white;
    transition-duration: 0.4s;
  }
  & a::after {
    right: 0;
    bottom: 0;
    transition-duration: 0.4s;
  }
  &::before {
    left: 0;
    top: 0;
    transition-duration: 0.4s;
  }
  & a::before {
    left: 0;
    top: 0;
    transition-duration: 0.4s;
  }
}

footer {
  column-gap: 12px;
  display: flex;
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
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
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
