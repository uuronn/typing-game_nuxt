<template>
  <div class="typing">
    <h2 class="typing__question">お題</h2>
    <p class="typing__romanAlphabet">ローマ字</p>
    <NuxtLink to="/">
      <button class="typing__home">ホーム</button>
    </NuxtLink>
  </div>
</template>

<style lang="scss" scoped>
.typing {
  text-align: center;

  &__romanAlphabet {
    font-size: 20px;
  }

  &__home {
    font-size: 80px;
  }
}
</style>
