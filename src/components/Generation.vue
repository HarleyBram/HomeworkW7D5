<template lang="html">
  <div>
  <h2>Carbon intensity of each energy source</h2>
  <table border=1>
    <tr v-for="(value, title, index) in generationData.data[0]" :title='title' :value='value'>
      <td>{{title}}</td>
      <td>{{value}}</td>
    </tr>
  </table>
</div>

</template>

<script>
export default {
  name: 'generation',
  props: ["generationData"]
}
</script>

<style lang="css" scoped>
</style>
