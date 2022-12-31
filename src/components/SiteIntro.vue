<template>
  <h1 class="title">Louise <br /><span>Rosenqvist</span></h1>
  <p>Front end developer with a curious mind and sense for design</p>
</template>

<script setup lang="ts">
defineProps<{
  msg: string
}>()
</script>

<style scoped lang="scss">
h1 {
  font-weight: 500;
  font-size: 3rem;
  height: fit-content;
  line-height: 0.8;
  top: -10px;
  width: fit-content;
  span {
    margin-left: 40px;
  }
}

p {
  font-size: 1.1rem;
  padding-top: 4px;
}
@media (min-width: 1024px) {
  h1 {
    font-size: 5vw;
    margin: 0;
    padding: 0;
  }
  p {
    font-size: 1.2rem;
  }
}
</style>
