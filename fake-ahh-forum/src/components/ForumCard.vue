<template>
    <div class="forum-card">
        <div class="details">
          <h3>
            <slot name="title"></slot>
          </h3>
          <slot></slot>
        </div>
        <div class="buttons">
          <button class="like-button"></button>
          <button class="favorite-button"></button>
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>

</style>