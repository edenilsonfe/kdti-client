<template>
  <header class="main-header">
    <div class="main-header-content content">
      <h3>KDTI</h3>
      <p>Owllish <a @click.prevent="logout">(Sair)</a></p>
    </div>
  </header>
</template>

<script>
import Cookie from 'js-cookie'

export default {
  methods: {
    logout() {
      Cookie.remove('auth')
      this.$store.commit('setAuth', null)
      this.$router.push('/login')
    },
  },
}
</script>

<style lang="sass" scoped>
@import '~/assets/sass/variables'

.main-header
  width: 100%
  height: $header-height
  background: $color-primary
  color: #FFF
  @media(min-width: 900px)
    padding-left: $aside-width
  h3, p, a
    margin: 0
    font-weight: 400
    color: #FFF
  a
    text-decoration: underline
    cursor: pointer
  &-content
    position: relative
    height: $header-height
    // background: #a8a8a8
    display: flex
    align-items: center
    justify-content: space-between
  .account-menu
    position: absolute
    right: 0
    top: 100%
    color: $color-primary
    list-style: none
    // display: none
    padding: 20px
    width: 120px
    box-shadow: 5px 5px 5px 5px black
</style>
