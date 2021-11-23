<template>
  <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" :width="width" :height="height">
    <g fill="none">
      <path d="M20 11H7.83l5.59-5.59L12 4l-8 8 8 8 1.41-1.41L7.83 13H20v-2z" fill="#da7f8f" />
    </g>
  </svg>
</template>

<script>
export default {
  props: {
    width: {
      type: [Number, String],
      default: '100%',
    },
    height: {
      type: [Number, String],
      default: '100%',
    },
  },
}
</script>
