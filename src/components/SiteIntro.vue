<template>
  <div class="greetings">
    <h1 class="green">Louise <span>Rosenqvist</span></h1>
    <h3>Front end developer with a curious mind and sense for design</h3>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  msg: string;
}>();
</script>

<style scoped lang="scss">
h1 {
  font-weight: 500;
  font-size: 6rem;
  line-height: 0.8;
  padding: 2rem 0;
  top: -10px;
  span {
    margin-left: 3.5rem;
  }
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
