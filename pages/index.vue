<template>
  <div class="container">
    <VStart/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import VTyping from '~/components/domain/game/VTyping.vue'
import VStart from '~/components/domain/home/VStart.vue'

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
