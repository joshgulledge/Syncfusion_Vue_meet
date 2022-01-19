<template>
  <div id="app">

   <!-- after we import syncfusion we can use the ejs-grid tag -->
   <ejs-grid :dataSource="localData">

   </ejs-grid>

  </div>
</template>

<script>

// imports
import Vue from 'vue';
import { GridPlugin } from '@syncfusion/ej2-vue-grids';


Vue.use(GridPlugin);
export default {
  // temp hardcode some data to be displayed in the grid
  data () {
    return {
      localData: [
      {orderId: 1, customerName: 'something', price: 57.26},
      {orderId: 2, customerName: 'anything', price: 237.96},
      {orderId: 3, customerName: 'everything', price: 176.92},
      {orderId: 4, customerName: 'nothing', price: 78.64}
    ]
    }
  }
}
</script>

<style>
  @import url(https://cdn.syncfusion.com/ej2/material.css);
</style>
