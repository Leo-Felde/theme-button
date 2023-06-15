<template>
  <div
    class="wrapper"
    :class="{'theme--dark' : themeDark}"
  >
    <ThemeButton @toggle-theme="changeTheme" />
  </div>
</template>

<script>
import { ref } from 'vue'

import ThemeButton from './components/ThemeButton.vue';

export default {
  name: 'App',
  components: {
    ThemeButton
  },

  setup () {
    const themeDark = ref(false)

    const changeTheme = () => {
      themeDark.value = !themeDark.value
    }

    return {
      themeDark,
      changeTheme
    }
  }
}
</script>

<style lang="sass">
@import "./styles/main.sass"

.wrapper
  width: 100%
  height: 100%
  display: flex
  background: #ced6d9
  transition: background-color 500ms linear
  &.theme--dark
    background: rgb(29, 39, 51) !important

#theme-button
  margin-left: auto
  margin-right: auto
  margin-top: auto
  margin-bottom: auto
</style>

