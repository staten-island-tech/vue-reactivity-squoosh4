<script setup>
import ForumCard from './ForumCard.vue'
import forumPosts from "../stores/posts.js"


function addToLikeList() {

  likedPosts.push(Number(this.id))

}

function addToFavoriteList(id) {

  favoritePosts.push(Number(this.id))

}

</script>

<template>
  <ForumCard v-for="post in forumPosts" :key="post.id">
    <template #title>{{ post.title }}</template>

    {{ post.body }}

  </ForumCard>
</template>


<!--
<template>
  <DestCard v-for="post in posts" :key="destination.name" :Destination="destination"/>
</template>
-->