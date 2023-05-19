<template lang="pug">
.features 
  .feature
    span.caption Featured works
    .feature__box(v-for="work in works" :key="work.title")
      img.feature__img(:src="work.img")
      .feature__right 
        .feature__title {{ work.title }}
        .feature__info
          .feature__year {{ work.year }}
          .feature__type {{ work.type }}
        .feature__text {{ work.text }}
</template>

<script>
import json from '@/assets/data/works.json'

export default {
  name: "AppFeatured",
  data() {
    return {
      works: json,
    }
  }
}
</script>

<style lang="sass" scoped>
.caption
  font-size: 1.5rem
.features
  padding: 5rem 22rem 5rem 8rem
  @media (max-width: 1000px)
    padding: 5rem

.feature

  display: flex
  flex-direction: column
  gap: 1.5rem

  &__img
    max-width: 20rem
    max-height: 12rem

  &__box
    display: flex
    gap: 2rem
    padding-bottom: 1rem
    border-bottom: 1px solid

    @media (max-width: 700px)
      flex-direction: column

  &__title
    font-size: 2rem
    font-family: 'Heebo Bold'
  &__info
    display: flex
    align-items: center
    gap: 3rem
    padding: 1rem 0
  &__year
    background-color: #16284E
    color: #fff
    padding: 0.5rem 1.2rem
    border-radius: 20px
  &__type 
    color: #B3BCC5
    font-size: 1rem
    font-family: 'Heebo Medium'
</style>