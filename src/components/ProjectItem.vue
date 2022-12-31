<template>
  <div class="project-item">
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
    <slot name="content"></slot>
    <div class="project-item__tags">
      <ul class="project-item__tags-container">
        <li v-for="(tag, index) in tags" :key="index" class="project-item__tags-obj">
          {{ tag }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { toRefs } from 'vue'

const props = defineProps({
  title: {
    type: String,
    default: ''
  },
  description: {
    type: String,
    default: ''
  },
  tags: {
    type: Array<String>,
    default: () => []
  }
})

const { title, description } = toRefs(props)
</script>
<style lang="scss" scoped>
.project-item {
  display: flex;
  flex-direction: column;
  row-gap: 16px;
  p {
    padding-bottom: 8px;
  }
  &__tags {
    column-gap: 8px;
    display: flex;
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem;
    font-weight: 300;
    &-obj {
      color: var(--vt-c-lilac);
      font-style: italic;
    }
    &-container {
      column-gap: inherit;
      display: flex;
      li {
        display: inline-block;
      }

      li:not(:last-of-type) {
        &::after {
          content: '';
          display: inline-block;
          height: 70%;
          width: 1.5px;
          background: #ebebeba3;
          position: relative;
          bottom: -4px;
          margin-left: 8px;
        }
      }
    }
  }
}
h3 {
  font-weight: 500;
  font-size: 1.4rem;
}
</style>
