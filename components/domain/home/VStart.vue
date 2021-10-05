<template>
  <div class="start">
    <h1 class="start__title">タイピングげーむ</h1>
    <div class="start__buttons">
      <NuxtLink to="/game/typing">
        <button class="start__button">
          はじめる
        </button>
      </NuxtLink>
      <NuxtLink to="/result/ranking">
        <button class="start__button">
          ランキング
        </button>
      </NuxtLink>
      <NuxtLink to="/setting/set">
        <button class="start__button">
          設定
        </button>
      </NuxtLink>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
    }
  },
  methods: {
    
  }
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

  &__buttons {
    display: flex;
    flex-direction: column;
    margin: auto;
    max-width: 500px;
    gap: 10px;
  }

  &__button {
    padding: 10px 0;
    border: 2px solid #000;
    border-radius: 10px;
    box-shadow: 5px 5px 0;
    font-size: 50px;
    color: $font-main;
    background: $ui-white;
    transition: 0.3s;
    width: 100%;

    &:hover {
      box-shadow: 0 0 0;
      transition: 0.3s;
      background: $ui-gray;
    }
  }
}
</style>
