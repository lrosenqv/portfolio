<template>
  <div v-for="(route, index) in routes" :key="`${route}-${index}`" class="nav-link__container">
    <RouterLink :to="route === 'Home' ? '/' : `/${route.toLocaleLowerCase()}`" class="nav-link">{{
      route
    }}</RouterLink>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import { RouterLink } from 'vue-router'
const props = defineProps({
  routes: {
    type: Array<string>,
    required: true
  }
})
const routes = ref<string[]>(props.routes)
</script>

<style lang="scss">
@keyframes linkBorder {
  0% {
    border-top: 2px solid white;
    height: 0;
    width: 0;
  }
  40% {
    height: 2px;
    width: 100%;
  }
  100% {
    border-top: 2px solid white;
    border-right: 2px solid white;
    height: 100%;
    width: 100%;
  }
}
.nav-link {
  color: var(--color-heading);
  display: inline-block;
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem;
  padding-inline: 10px;
  z-index: 1;

  &__container {
    width: fit-content;
    &::before,
    &::after {
      content: '';
      display: block;
      position: absolute;
    }

    &:hover {
      &::before {
        animation: linkBorder 0.3s;
        animation-fill-mode: forwards;
      }
      &::after {
        animation: linkBorder 0.3s;
        animation-fill-mode: forwards;
        right: 0;
        animation-delay: 0.3s;
        transform: rotate(180deg) translateY(100%);
      }
    }
  }
}
a.router-link-exact-active {
  color: var(--vt-c-lilac);
}
</style>
