<template>
  <div class="start">
    <h1 class="start__title">タイピングげーむ</h1>
    <div class="start__container">
      <NuxtLink to="/game/typing" class="start__link">
        <div class="start__wrapper">
          <button class="start__button">
            はじめる
          </button>
        </div>
      </NuxtLink>
      <NuxtLink class="start__link" to="/result/ranking">
        <div class="start__wrapper">
          <button class="start__button">
            ランキング
          </button>
        </div>
      </NuxtLink>
      <NuxtLink class="start__link" to="/setting/set">
        <div class="start__wrapper">
          <button class="start__button">
            設定
          </button>
        </div>
      </NuxtLink>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.start {
  text-align: center;
  background: #674598;
  height: 100vh;
  padding: 16px;

  &__title {
    margin: 40px 0 80px;
    font-size: 80px;
  }

  &__container {
    display: flex;
    flex-direction: column;
    margin: auto;
    max-width: 500px;
    gap: 10px;
  }

  &__link {
    text-decoration: none;
  }

  &__wrapper {
    position: relative;
    width: 100%;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    background: rgba(0,0,0,0.5);
    overflow: hidden;
    border-radius: 20px;

    &:hover:before {
      content: '';
      position: absolute;
      width: 120%;
      height: 30%;
      background: linear-gradient(#00ccff, #d400d4);
      animation: animate 4s linear infinite;
    }

    &::after {
      content: '';
      position: absolute;
      inset: 4px;
      background: $ui-gray;
      border-radius: 18px;
    }

    @keyframes animate {
      0% {
        transform: rotate(0deg);
      }
      100% {
        transform: rotate(720deg);
      }
    }
  }

  &__button {
    position: relative;
    z-index: 10;
    font-size: 30px;
    color: #000;
  }
}
</style>
