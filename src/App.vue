<template>
  <div id="app">
    <img alt="NoteAddApp logo" src="./assets/logo.png">
    <Notes/>
    <FooterCustom/>
  </div>
</template>

<script>
import Notes from './components/Notes.vue'
import FooterCustom from './components/FooterCustom.vue'

export default {
  name: 'App',
  components: {
    Notes,FooterCustom
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Rubik&display=swap');

#app {
  font-family: 'Rubik', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
html{
  background-color: #e8f9e9;
}
</style>
