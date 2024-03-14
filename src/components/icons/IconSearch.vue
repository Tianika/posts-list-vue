<template>
  <svg
    version="1.0"
    xmlns="http://www.w3.org/2000/svg"
    :width="width"
    :height="height"
    :viewBox="viewBox"
    preserveAspectRatio="xMidYMid meet"
  >
    <g
      transform="translate(0.000000,64.000000) scale(0.100000,-0.100000)"
      :fill="fill"
      stroke="none"
    >
      <path
        d="M206 578 c-60 -16 -130 -91 -145 -154 -24 -100 20 -194 114 -239 63
-31 123 -31 188 0 l39 18 79 -79 c75 -74 80 -77 96 -61 16 16 13 21 -61 96
l-79 79 18 39 c32 66 31 130 -2 193 -48 90 -149 135 -247 108z m145 -71 c49
-32 83 -105 74 -159 -10 -60 -73 -123 -133 -133 -55 -9 -127 25 -160 75 -30
45 -28 130 6 177 45 64 148 83 213 40z"
      />
    </g>
  </svg>
</template>

<script setup>
const { fill, width, height, viewBox } = defineProps({
  fill: {
    type: String,
    default: '#000000'
  },
  width: {
    type: String,
    default: '64'
  },
  height: {
    type: String,
    default: '64'
  },
  viewBox: {
    type: String,
    default: '0 0 64 64'
  }
})
</script>
