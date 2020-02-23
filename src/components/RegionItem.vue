<template lang="html">
  <li v-on:click='handleClick'>{{region.shortname}}
  </li>
</template>

<script>
import {eventBus} from '../main.js';

export default {
name: 'region-item',
props: ['region'],
  methods:{
    handleClick(){
      eventBus.$emit('region-selected', this.region)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
