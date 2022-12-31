<template>
  <ProjectItem
    title="blanc."
    description="School assignment for one of our design courses. The assignment was to create a landingpage of our own choosing.
    I chose to create a dummy product: blanc. - a skin care brand with a product line of face masks. The idea was a brand that offers
    natural products with organic ingredients, therefore I went with an earthy color theme, simple design without any excessive
    knicknacks, matching the product. All pictures used in the design is created in blender"
    :tags="['design', 'school assignment', 'figma']"
  >
    <template #content>
      <div class="content-wrapper">
        <ProjectImage :img-src="blancDesktop" />
        <ProjectImage :img-src="blancTablet" />
        <ProjectImage :img-src="blancMobile" />
      </div>
    </template>
  </ProjectItem>
</template>
<script setup lang="ts">
import blancDesktop from '@/assets/blanc/desktop.jpg'
import blancTablet from '@/assets/blanc/tablet.jpg'
import blancMobile from '@/assets/blanc/mobile.jpg'
import ProjectImage from './ProjectImage.vue'
import ProjectItem from './ProjectItem.vue'
</script>

<style lang="scss" scoped>
.content-wrapper {
  column-gap: 12px;
  display: grid;
  grid-template-columns: 50% 30% auto;
  height: 20rem;
  position: relative;
  :nth-child(1) {
    grid-column: 1;
    place-self: end left;
    transform-origin: bottom left;
  }
  :nth-child(2) {
    grid-column: 2;
    transition: all 0.5s;
    place-self: end center;
    &:hover {
      width: 80%;
      transform-origin: bottom center;
    }
  }
  :nth-child(3) {
    grid-column: 3;
    place-self: end right;
    &:hover {
      width: 60%;
      transform-origin: right;
    }
  }
  @keyframes createBox {
    from {
      height: 100%;
      margin-right: -5px;
      position: relative;
    }
    to {
      grid-row: 1 /-1;
      height: 200%;
    }
  }

  div {
    grid-row: 1;
    overflow: hidden;
    transition: all 0.5s;

    &:hover {
      animation: createBox 0.5s;
      animation-fill-mode: forwards;
      grid-column: 1 / -1;
      overflow: auto;
    }
  }
}
</style>
