<template>
  <div class="typing">
    <div class="typing__group">
      <h2 class="typing__question">お題</h2>
      <p class="typing__romanAlphabet">ローマ字</p>
    </div>
    <NuxtLink to="/" class="typing__wrapper">
      <button class="typing__home">ホーム</button>
    </NuxtLink>
  </div>
</template>

<script>
export default {
  data() {
    return {
    }
  }
}
</script>


<style lang="scss" scoped>
.typing {
  text-align: center;
  background: $ui-main;
  height: 100vh;
  padding: 10px;

  &__question {
    margin: 40px 0 80px;
    font-size: 80px;
  }

  &__romanAlphabet {
    font-size: 20px;
  }

  &__wrapper {
    position: absolute;
    z-index: 1;
    top: 0;
    right: 0;
  }

  &__home {
    
  }
}
</style>
