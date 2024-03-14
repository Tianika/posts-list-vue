<script setup>
const props = defineProps({
  title: {
    type: String,
    default: ''
  },
  body: {
    type: String,
    default: ''
  },
  author: {
    type: String,
    required: ''
  }
})
</script>

<template>
  <div class="post-item">
    <h3 class="post-item__title">{{ props.title }}</h3>
    <div class="post-item__body">
      {{ props.body }}
    </div>
    <div class="post-item__author">
      {{ props.author }}
    </div>
  </div>
</template>

<style lang="scss">
.post-item {
  break-inside: avoid-column;
  margin-bottom: 15px;
  padding: 15px;
  background-color: var(--color-card);
  border: 1px solid var(--color-border);

  &__title {
    font-size: 18px;
    line-height: 22px;
    font-weight: bold;
    color: var(--color-header-text);

    &:first-letter {
      text-transform: uppercase;
    }
  }

  &__body {
    margin-top: 10px;
    font-weight: bold;

    &:first-letter {
      text-transform: uppercase;
    }
  }

  &__author {
    margin-top: 15px;
    opacity: var(--opacity);
  }
}
</style>
