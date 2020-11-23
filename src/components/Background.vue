<template>
  {{ color.slice(1).toUpperCase() }}
</template>
<script>
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
  data() {
    return {
      color: '',
    };
  },
  methods: {
    getRandom() {
      return values[Math.floor(Math.random() * values.length)];
    },
    generateColorHex() {
      return `#${this.getRandom()}${this.getRandom()}${this.getRandom()}${this.getRandom()}${this.getRandom()}${this.getRandom()}`;
    },
  },
  mounted() {
    this.color = this.generateColorHex();
    document.body.style.backgroundColor = this.color;
  },
};
</script>
