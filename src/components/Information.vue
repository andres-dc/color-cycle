<template>
  <div class="information">
    <table>
      <tbody>
        <tr>
          <td>Hex</td>
          <td>{{ colorHex.toUpperCase() }}</td>
        </tr>
        <tr>
          <td>RGB</td>
          <td>{{ rgb }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'Information',
  props: ['colorHex', 'rgb'],
};
</script>

<style lang="scss">
.information {
  width: 20%;
  background: white;
  opacity: 0.5;

  table {
    width: 100%;
    text-align: center;
  }
}
</style>
