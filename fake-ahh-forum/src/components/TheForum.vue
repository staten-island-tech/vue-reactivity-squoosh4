<script setup>
import ForumCard from './ForumCard.vue'

const posts
</script>

<template>
  <ForumCard v-for="(title, body) in posts">
    <template #heading>{{ title }}</template>

    {{ body }}
  </ForumCard>
</template>
