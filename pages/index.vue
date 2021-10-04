<template>
  <div class="container">
    <VStart/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import VStart from '~/components/domain/home/VStart.vue'
import VTyping from '~/components/domain/game/VTyping.vue'

export default Vue.extend({
  components: {
    VTyping,
    VStart
  }
})
</script>

<style lang="scss" scoped>
.container {
  margin: 0 auto;
}
</style>
