<template>
  <Information :colorHex="colorHex" :rgb="hexToRGB(colorHex)" />
</template>

<script>
import Information from './components/Information.vue';

const values = [
  '0',
  '1',
  '2',
  '3',
  '4',
  '5',
  '6',
  '7',
  '8',
  '9',
  'a',
  'b',
  'c',
  'd',
  'e',
  'f',
];

export default {
  name: 'App',
  data() {
    return {
      colorHex: '',
    };
  },
  components: {
    Information,
  },
  methods: {
    getRandom() {
      return values[Math.floor(Math.random() * values.length)];
    },
    generateColorHex() {
      return `${this.getRandom()}${this.getRandom()}${this.getRandom()}${this.getRandom()}${this.getRandom()}${this.getRandom()}`;
    },
    hexToRGB(hex) {
      let rgb = hex.match(/.{1,2}/g);
      return `R: ${parseInt(rgb[0], 16)}, G: ${parseInt(
        rgb[1],
        16
      )}, B: ${parseInt(rgb[2], 16)}`;
    },
  },
  beforeMount() {
    this.colorHex = this.generateColorHex();
    document.body.style.backgroundColor = `#${this.colorHex}`;
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
