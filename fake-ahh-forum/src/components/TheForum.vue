<script setup>
import ForumCard from './ForumCard.vue'
import forumPosts from "../stores/posts.js"
import likedPosts from "../stores/likeList.js"
import favoritePosts from "../stores/favoriteList.js"


function addToLikeList() {

likedPosts[Number(this.id) - 1] = Number(this.id)

}

function addToFavoriteList() {

favoritePosts[Number(this.id) - 1] = Number(this.id)

}

function removeFromLikeList() {

likedPosts[Number(this.id) - 1] = 0

}

function removeFromFavoriteList() {

favoritePosts[Number(this.id)] = 0

}

function likedPostChecker() {
  forumPosts.filter(post.id === likedPosts[post.id - 1])
}

function favoritePostChecker() {
  forumPosts.filter(post.id === favoritePosts[post.id - 1])
}

</script>

<template>
  <div class="post-container">
    <ForumCard v-for="post in forumPosts" :key="post.id">
    <template #title>{{ post.title }}</template>

    {{ post.body }}

    <div class="buttons">
          <button class="like-button" @click="addToLikeList">👍</button>
          <button class="favorite-button" @click="addToFavoriteList">💖💞💕</button>
    </div>
    </ForumCard>
    <div class="like-list-holder">
      <h2>liked posts</h2>
      <ForumCard v-for="post in likedPostChecker" :key="post.id + 3">
      <template #title>{{ post.title }}</template>

        {{ post.body }}
        
      <div class="buttons">
          <button class="like-button" @click="removeFromLikeList">👎</button>
      </div>
      </ForumCard>
    </div>
    <div class="favorite-list-holder">
      <h2>favorite posts </h2>
      <ForumCard v-for="post in favoritePostChecker" :key="post.id + 6">
      <template #title>{{ post.title }}</template>

        {{ post.body }}
        
      <div class="buttons">
          <button class="favorite-button" @click="removeFromFavoriteList">💔</button>
      </div>
      </ForumCard>
    </div>
  </div>
</template>


<!--
<template>
  <DestCard v-for="post in posts" :key="destination.name" :Destination="destination"/>
</template>
-->