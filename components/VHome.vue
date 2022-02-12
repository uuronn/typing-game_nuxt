<template>
  <NuxtLink to="/" class="home">
    <div class="home__wrapper">
      <button class="home__button">ホーム</button>
    </div>
  </NuxtLink>
</template>

<style lang="scss" scoped>
.home {
  position: absolute;
  z-index: 1;
  top: 8px;
  right: 8px;
  text-decoration: none;

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

  &__button {
    position: relative;
    z-index: 10;
    font-size: 18px;
    color: #000;
  }
}
</style>
