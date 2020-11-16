<template>
  <div id="app" :style="{color: textColor, backgroundColor: backgroundColor}">
    <Resume
      :highlightColor="highlightColor"
      :backgroundColor="backgroundColor"
      :textColor="textColor"
    />
    <div class="mode-button-container">
      <Button
        class="mode-button"
        width="300px"
        height="50px"
        :color="highlightColor"
        labelColor="textColor"
        label="Set Custom Colors"
        @buttonClick="showCustomModeModal = !showCustomModeModal"
      >
      </Button>
      <div>
        <input type="checkbox" id="custom-color-mode-checkbox" name="custom-color-mode-checkbox" v-model="isCustomColorMode">
        <label for="custom-color-mode-checkbox">Custom Color Mode</label>
      </div>
    </div>
    <Modal
      :backgroundColor="backgroundColor"
      :highlightColor="highlightColor"
      v-if="showCustomModeModal"
    >
    <div class="color-selectors">
      <div class="color-selector">
        <input type="color" id="highlight-color-selector" name="highlight-color-selector" v-model="selectedHighlightColor">
        <label for="highlight-color-selector">Highlight Color</label>
      </div>
      <div class="color-selector">
        <input type="color" id="text-color-selector" name="text-color-selector" v-model="selectedTextColor">
        <label for="text-color-selector">Text Color</label>
      </div>
      <div class="color-selector">
        <input type="color" id="background-color-selector" name="background-color-selector" v-model="selectedBackgroundColor">
        <label for="background-color-selector">Background Color</label>
      </div>
    </div>
    </Modal>
  </div>
</template>

<script>
import Button from './components/Button.vue'
import Resume from './components/Resume.vue'
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Button,
    Resume,
    Modal,
  },
  data() {
    return {
      isCustomColorMode: false,
      languages: ['Javascript', 'Python', 'HTML & CSS', 'Go', 'C++'],
      selectedHighlightColor: 'black',
      selectedTextColor: 'black',
      selectedBackgroundColor: 'black',
      showCustomModeModal: false,
      skills: ['Vue.js', 'Node.js', 'Agile Development', 'Git Version Control', 'Remote Work'],
    }
  },
  computed: {
    highlightColor() { return this.isCustomColorMode ? this.selectedHighlightColor : '#9cd2d6'},
    backgroundColor() { return this.isCustomColorMode ? this.selectedBackgroundColor : 'white' },
    textColor() { return this.isCustomColorMode ? this.selectedTextColor : '#2c3e50'},
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

.mode-button-container {
  position: absolute;
  right: 10px;
  bottom: 10px;

}
.mode-button {
  margin: 5px;
}

.color-selectors {
  display: flex;
  flex-direction: column;
}
.color-selector {
  padding: 10px;
}
</style>
