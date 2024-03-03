<script setup>
import ForumCard from './ForumCard.vue'


</script>

<template>
  <ForumCard v-for="(title, body) in posts">
    <template #heading>{{ title }}</template>

    {{ body }}
  </ForumCard>
</template>


<template>
  <DestCard v-for="post in posts" :key="destination.name" :Destination="destination"/>
</template>
