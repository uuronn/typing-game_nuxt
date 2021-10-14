<template>
  <main class="container">
    <VStart/>
  </main>
</template>

<script lang="ts">
import Vue from 'vue'
import VStart from '~/components/domain/home/VStart.vue'

export default Vue.extend({
  components: {
    VStart
  }
})
</script>

<style lang="scss" scoped>
.container {
  margin: 0 auto;
}
</style>
