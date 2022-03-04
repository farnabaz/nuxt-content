<template>
  <div>
    <Content v-if="content" :id="content.id" />
    <div v-else>Page not found</div>
  </div>
</template>

<script setup lang="ts">
const route = useRoute()


const { data: content } = await useAsyncData('content', () => useContentQuery(route.path).findOne())
</script>
