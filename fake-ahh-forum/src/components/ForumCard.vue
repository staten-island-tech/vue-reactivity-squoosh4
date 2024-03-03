<script>
    function addToLikeList() {

    }

    function addToFavoriteList() {

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
        <slot name="image"></slot>
        <div class="buttons">
          <button class="like-button" @click="addToLikeList">👍</button>
          <button class="favorite-button" @click="addToFavoriteList">💖💞💕</button>
        </div>
    </div>
</template>

<style lang="scss" scoped>

</style>