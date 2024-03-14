<script setup>
import PostItem from './PostItem.vue'

const props = defineProps({
  posts: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <div class="posts-list">
    <PostItem
      v-for="{ id, title, body, author } in props.posts"
      :key="id"
      :title="title"
      :body="body"
      :author="author"
    ></PostItem>
  </div>
</template>

<style lang="scss">
.posts-list {
  -webkit-column-count: 3;
  -moz-column-count: 3;
  column-count: 3;
  -moz-column-fill: balance;
  column-fill: balance;
  gap: 15px;

  @media (max-width: 1024px) {
    -webkit-column-count: 2;
    -moz-column-count: 2;
    column-count: 2;
  }
  @media (max-width: 540px) {
    -webkit-column-count: 1;
    -moz-column-count: 1;
    column-count: 1;
  }
}
</style>
