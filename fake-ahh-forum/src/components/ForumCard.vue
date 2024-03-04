<script setup>

import likedPosts from "../stores/likeList.js"
import favoritePosts from "../stores/favoriteList.js"


function addToLikeList() {

likedPosts.push(Number(this.id))

}

function addToFavoriteList() {

favoritePosts.push(Number(this.id))

}


</script>

<template>
    <div class="forum-card">
        <div class="details">
          <h3>
            <slot name="title"></slot>
          </h3>
          <slot></slot>
        </div>
        <div class="buttons">
          <button class="like-button" @click="addToLikeList">👍</button>
          <button class="favorite-button" @click="addToFavoriteList">💖💞💕</button>
      </div>
    </div>
</template>

<style lang="scss" scoped>

</style>