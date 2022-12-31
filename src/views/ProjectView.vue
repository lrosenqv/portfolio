<script setup lang="ts">
import ProjectsList from '@/components/ProjectsList.vue'
</script>

<template>
  <div class="projects-list">
    <div class="projects-list-items">
      Site in progress, will be updated soon.. <br /><br />
      <ProjectsList />
    </div>
  </div>
</template>

<style lang="scss">
.projects-list {
  grid-row: 2 / 13;
  &-items {
    height: 100%;
  }
}
</style>
