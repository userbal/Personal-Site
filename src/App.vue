<template>
  <div id="app" :style="{backgroundColor: backgroundColor}">
    <Resume
      :highlightColor="highlightColor"
      :backgroundColor="backgroundColor"
      :textColor="textColor"
    />
    <Button
      class="dark-mode-button"
      width="200px"
      height="50px"
      :color="highlightColor"
      labelColor="textColor"
      :label="isDarkMode ? 'Light Mode' : 'Dark Mode'"
      @buttonClick="isDarkMode = !isDarkMode"
    >
    </Button>
  </div>
</template>

<script>
import Button from './components/Button.vue'
import Resume from './components/Resume.vue'

export default {
  name: 'App',
  components: {
    Button,
    Resume,
  },
  data() {
    return {
      isDarkMode: false,
      skills: ['Vue.js', 'Node.js', 'Agile Development', 'Git Version Control', 'Remote Work'],
      languages: ['Javascript', 'Python', 'HTML & CSS', 'Go', 'C++'],
    }
  },
  computed: {
    highlightColor() { return this.isDarkMode ? 'red' : '#9cd2d6' },
    backgroundColor() { return this.isDarkMode ? '#2c3e50' : '#FFFFFF' },
    textColor() { return this.isDarkMode ? '#FFFFFF' : '#2c3e50' },
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0px;
  padding: 0px;
  height: 100vh;
  width: 100vw;
  overflow: hidden;
}

body {
  margin: 0px;
}

.dark-mode-button {
  position: absolute;
  right: 10px;
  bottom: 10px;

}
</style>
