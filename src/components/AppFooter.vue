<template lang="pug">
footer.footer
  .footer__list 
    a(:href="label.link" target="_blank" v-for="label in labels" :key="label.title")
      img.footer__item(:src="label.img" :alt="label.title")
  p.footer__copyright Copyright ©2020 All rights reserved 
</template>

<script>
export default {
  name: "AppFooter",
  data() {
    return {
      labels: [
        { "title": "facebook", "img": "/src/assets/images/facebook.svg", "link": "https://www.facebook.com" },
        { "title": "instagram", "img": "/src/assets/images/instagram.svg", "link": "https://www.instagram.com" },
        { "title": "twitter", "img": "/src/assets/images/twitter.svg", "link": "https://www.twitter.com" },
        { "title": "linkedin", "img": "/src/assets/images/linkedin.svg", "link": "https://www.linkedin.com" },
      ],
    }
  },
}
</script>

<style lang="sass" scoped>
.footer
  padding: 5rem
  display: flex
  flex-direction: column
  justify-content: center
  align-items: center

  &__list
    display: flex
    gap: 2rem
    padding: 1rem
</style>