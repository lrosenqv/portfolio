<template>
  <div class="content-img" @mouseleave="(e) => onMouseOut(e)">
    <img :src="imgSrc" />
  </div>
</template>
<script lang="ts" setup>
import { toRefs } from 'vue'
const props = defineProps({
  imgSrc: {
    type: String,
    default: ''
  }
})
const { imgSrc } = toRefs(props)
function onMouseOut(e: MouseEvent) {
  const el = e.target as HTMLDivElement
  el.scrollTo(0, 0)
}
</script>
<style lang="scss" scoped>
.content-img {
  align-content: center;
  border: 3px solid var(--color-decoration-secondary);
  border-radius: 4px;
  display: flex;
  flex-direction: column;
  height: 100%;
  overflow: auto;
  position: relative;
  width: 100%;

  &:hover {
    background: var(--color-background);
    border: 6px solid var(--color-decoration-primary);
    position: absolute;
    z-index: 2;

    img {
      height: max-content;
      position: absolute;
      width: 100%;
    }
  }

  img {
    width: 100%;

    &:hover {
      cursor: pointer;
      overflow: auto;
    }
  }
}
</style>
