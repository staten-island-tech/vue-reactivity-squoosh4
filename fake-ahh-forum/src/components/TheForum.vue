<script setup>
import ForumCard from './ForumCard.vue'
import forumPosts from "../stores/posts.js"
import favoritePosts from "../stores/favoriteList.js"
import likedPosts from "../stores/likeList.js"

function addToLikeList() {

  likedPosts.push(Number(this.id))

}

function addToFavoriteList(id) {

  favoritePosts.push(Number(this.id))

}

</script>

<template>
  <ForumCard v-for="post in forumPosts">
    <template #title>{{ post.title }}</template>

    {{ post.body }}

    <div class="buttons" v-bind="{id: post.id}">
          <button class="like-button" @click="addToLikeList">👍</button>
          <button class="favorite-button" @click="addToFavoriteList">💖💞💕</button>
    </div>
  </ForumCard>
</template>


<!--
<template>
  <DestCard v-for="post in posts" :key="destination.name" :Destination="destination"/>
</template>
-->