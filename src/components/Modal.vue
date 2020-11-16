<template>
    <div
      id="modal"
      :style="{width: width, height: height, backgroundColor: backgroundColor, borderColor: highlightColor}"
    >
      <slot></slot>
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
    backgroundColor: {
      required: false,
      type: String,
      default: 'white',
    },
    highlightColor: {
      required: false,
      type: String,
      default: 'white',
    }
  },
}
</script>

<style scoped>
  #modal {
    position: absolute;
    display: flex;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 4px 12px 0 rgba(0,0,0,0.4);
    transition: 0.3s;
    border-radius: 8px;
    border: solid 1px;
  }
</style>
