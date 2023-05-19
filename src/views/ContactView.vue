<template lang="pug">
AppHeader(:currentIndex="2")
</template>

<script>
import AppHeader from '@/components/AppHeader.vue'
export default {
  name: "ContactView",
  components: {
    AppHeader,
  }
}
</script>

<style lang="scss" scoped></style>