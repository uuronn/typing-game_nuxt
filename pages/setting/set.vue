<template>
  <div class="set">
    <h2>設定ページ</h2>
    <NuxtLink to="/" class="set__link">
      <button class="set__home">ホーム</button>
    </NuxtLink>
  </div>
</template>

<style lang="scss" scoped>
.set {
  text-align: center;
  background: $ui-main;
  height: 100vh;
  padding: 10px;

  &__link {
    position: absolute;
    z-index: 1;
    top: 0;
    right: 0;
  }
}
</style>
