<template>
  <div class="button no-select" :style="buttonStyle" @click="$emit('buttonClick')" >
    <slot id="icon"></slot>
    <div>
      {{label}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'button',
  props: {
    height: {
      type: String,
      required: true,
    },
    width: {
      type: String,
      required: true,
    },
    color: {
      type: String,
      required: false,
      default: 'white',
    },
    label: {
      type: String,
      required: true,
    },
    labelColor: {
      type: String,
      required: false,
      default: 'black',
    },
    icon :{
      type: String,
      required: false,
    },
  },
  computed: {
    buttonStyle() {
      return `width: ${this.width}; height: ${this.height}; background-color: ${this.color}; color: ${this.labelColor}`
    }
  },
}
</script>

<style scoped>
  .button {
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 25px;
    opacity: 0.9;
    font-weight: bold;
  }
  .button:hover {
    opacity: 1;
    cursor: pointer;
  }

  #icon {
    padding-bottom: 10px;
  }
</style>
