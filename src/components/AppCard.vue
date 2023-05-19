<template lang="pug">
.card
  .card__left
    h1.card__title 
      span Hi, I'm Luka,
      br
      span Frontend Developer 
    p.card__subtitle Amet minim mollit non deserunt ullamco est sit aliqua dolor do amet sint. Velit officia consequat duis enim velit mollit. Exercitation veniam consequat sunt nostrud amet.
    button.card__download Download Resume
  .card__right
    img.card__avatar(src="@images/avatar.jpg" alt="avatar")
</template>

<script>
export default {
  name: "AppCard",
}
</script>

<style lang="sass" scoped>
.card
  display: flex
  padding: 5rem 8rem
  gap: 10rem
  
  @media (max-width: 1000px)
    padding: 5rem
    flex-direction: column

    &__left
      order: 2

  &__avatar
    border-radius: 50%
    width: 20rem
    box-shadow: -13px 15px 8px 0px rgba(34, 60, 80, 0.2)
  
  &__subtitle
    padding: 1rem 0
    max-width: 60rem

  &__download
    background-color: #FB6167
    color: #fff
    text-transform: uppercase
    padding: 1rem 2rem
    border: none
    font-family: 'Heebo Bold'
</style>