<script setup>
import { ref, onBeforeMount, computed } from 'vue'

import SearchInput from '@/components/SearchInput.vue'
import PostsList from '@/components/PostsList.vue'

import { getPosts } from '@/api/posts/get_posts'
import { getUsers } from '@/api/posts/get_users'

const postsList = ref([])
const usersMap = ref({})
const searchText = ref('')

const filteredPosts = computed(() =>
  postsList.value.filter((post) =>
    post.author.toLowerCase().includes(searchText.value.toLowerCase())
  )
)

const getPostsRequest = async () => {
  const [posts, users] = await Promise.all([getPosts(), getUsers()])

  usersMap.value = users.reduce((acc, user) => {
    acc[user.id] = user

    return acc
  }, {})

  postsList.value = posts.map((post) => ({
    ...post,
    author: usersMap.value[post.userId]?.name
  }))
}

onBeforeMount(() => {
  getPostsRequest()
})
</script>

<template>
  <div class="posts">
    <SearchInput v-model="searchText" />
    <PostsList :posts="filteredPosts" />
    <div v-if="searchText && !filteredPosts.length">Ничего не найдено</div>
  </div>
</template>

<style lang="scss">
.posts {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}
</style>
