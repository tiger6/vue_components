<template>
  <div class="rate-mod">
    <span v-for="i in num" :key="i" @click="edit(i)" >
      <i style="font-family: 'crank' !important;" :class="[ voidIcon !== '' && i > value ? voidIcon : icon]" :style="{color: i > value ? voidColor : color, 'font-size': size}">&#xe616;</i>
    </span>
  </div>
</template>
<script>
export default {
  name: 'Rate',
  props: {
    value: {
      type: Number,
      default: 0
    },
    num: {
      type: Number,
      default: 5
    },
    disabled: {
      type: Boolean,
      default: false
    },
    size: {
      type: String,
      default: '2rem'
    },
    icon: {
      type: String,
      default: 'rate'
    },
    voidIcon: {
      type: String,
      default: ''
    },
    color: {
      type: String,
      default: '#ffd21e'
    },
    voidColor: {
      type: String,
      default: '#EFEFEF'
    }
  },
  methods: {
    edit (num) {
      if (!this.disabled) this.$emit('input', num)
    }
  }
}
</script>

<style>
@font-face {
  font-family: 'crank';  /* project id 886927 */
  src: url('//at.alicdn.com/t/font_886927_kxey1nxy84.eot');
  src: url('//at.alicdn.com/t/font_886927_kxey1nxy84.eot?#iefix') format('embedded-opentype'),
  url('//at.alicdn.com/t/font_886927_kxey1nxy84.woff2') format('woff2'),
  url('//at.alicdn.com/t/font_886927_kxey1nxy84.woff') format('woff'),
  url('//at.alicdn.com/t/font_886927_kxey1nxy84.ttf') format('truetype'),
  url('//at.alicdn.com/t/font_886927_kxey1nxy84.svg#tq-v5') format('svg');
}
</style>
