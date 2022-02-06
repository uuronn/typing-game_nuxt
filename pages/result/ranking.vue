<template>
  <div class="ranking">
    <h2>ランキングページ</h2>
    <NuxtLink to="/" class="ranking__link">
      <div class="ranking__wrapper">
        <button class="ranking__home">ホーム</button>
      </div>
    </NuxtLink>
  </div>
</template>

<style lang="scss" scoped>
.ranking {
  text-align: center;
  background: #674598;
  height: 100vh;
  padding: 10px;

  &__link {
    position: absolute;
    z-index: 1;
    top: 8px;
    right: 8px;
    text-decoration: none;
  }

  &__wrapper {
    position: relative;
    width: 150px;
    height: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
    background: rgba(0,0,0,0.5);
    overflow: hidden;
    border-radius: 10px;

  
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
      border-radius: 7px;
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

  &__home {
    position: relative;
    z-index: 10;
    font-size: 18px;
    color: #000;
  }
}
</style>
