<template>
  <div class="start">
    <h1 class="start__title">タイピングげーむ</h1>
    <NuxtLink to="/game/typing">
      <button class="start__button">
        START
      </button>
    </NuxtLink>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.start {
  text-align: center;
  background: $ui-main;
  height: 100vh;
  padding: 10px;

  &__title {
    margin: 40px 0 80px;
    font-size: 80px;
  }

  &__button {
    font-size: 80px;
    color: $font-main;
    background: $ui-gray;
  }
}
</style>
