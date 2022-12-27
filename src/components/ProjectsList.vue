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
import blancDesktop from "@/assets/blanc/desktop.jpg";
import blancTablet from "@/assets/blanc/tablet.jpg";
import blancMobile from "@/assets/blanc/mobile.jpg";
import ProjectImage from "./ProjectImage.vue";
import ProjectItem from "./ProjectItem.vue";
</script>

<style lang="scss" scoped>
.content-wrapper {
  display: grid;
  grid-template-columns: 50% auto auto;
  height: 20rem;
  position: relative;
  width: 100%;
  :nth-child(1) {
    justify-self: start;
  }
  :nth-child(2) {
    justify-self: center;
  }
  :nth-child(3) {
    justify-self: end;
  }

  div {
    grid-row: 1;
    overflow: auto;
    scrollbar-width: thin;
    transition: all 0.5s;
    width: 95%;
    &::-webkit-scrollbar {
      width: 0;
    }
    &:hover {
      height: 120%;
      overflow: auto;
      position: absolute;
      width: 100%;
    }
  }
}
</style>
