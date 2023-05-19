<template lang="pug">
header.header
  ul.header__list(v-if="isLargeScreen")
    RouterLink(:to="{ name: value.name }" v-for="(value, index) in arr") 
      li.header__item(:class="{active: index == currentIndex}") {{value.title}}
  .burger(v-else)
    img(:src="menuVisible ? '/src/assets/images/close.svg' : 'src/assets/images/menu.svg'" alt="burger" @click="menuVisible = !menuVisible")
    .burger__menu(v-show="menuVisible")
      RouterLink(:to="{ name: value.name }" v-for="value in arr") 
        li.header__item {{value.title}}
        
</template>

<script>
import { useMediaQuery } from '@vueuse/core'

export default {
  name: "AppHeader",
  props: ["currentIndex"],
  data() {
    return {
      arr: [
        { "title": "Works", "name": "works" },
        { "title": "Blog", "name": "blog" },
        { "title": "Contact", "name": "contact" },
      ],
      menuVisible: false,
      isLargeScreen: useMediaQuery('(min-width: 700px)'),
    }
  },
}
</script>

<style lang="sass" scoped>

.active
  color: #FB6167
.header
  padding: 3rem
  &__list
    display: flex
    justify-content: right
    gap: 3rem

.burger
  cursor: pointer
  display: flex
  justify-content: right
  align-items: flex-end
  flex-direction: column
</style>