<template>
  <div id="app">

    <button v-on:click="buttonClick">
      Load Data
    </button>
   <!-- after we import syncfusion we can use the ejs-grid tag -->
   <ejs-grid ref="dataGrid">
     <!-- using a ref to get the data returned from ajax -->
     <e-columns>
       <!-- include the column sub tab -->
       <e-column 
        field="OrderID"
        headerText="Order Id" 
        textAlign="Right">
       </e-column>
        <!-- field = Variable Name / headerText = Displayed Name -->
       <e-column 
        field="CustomerID"
        headerText="Customer Id" 
        textAlign="Right">
       </e-column>

       <e-column 
        field="ShipCountry"
        headerText="Ship Country">
       </e-column>

       <e-column 
        field="OrderDate"
        headerText="Order Date" 
        textAlign="Right"
        format="yMd"
        type="data"
        width="120">
       </e-column>

     </e-columns>

   </ejs-grid>

  </div>
</template>

<script>

// imports
import Vue from 'vue';
import { GridPlugin } from '@syncfusion/ej2-vue-grids';
import { Ajax } from '@syncfusion/ej2-base';

Vue.use(GridPlugin);

export default {
  // temp hardcode some data to be displayed in the grid
  data () {
    return {
     
    }
  },
  methods: {
    buttonClick: function() {
      // define the ref variable for the grid 
      let grid = this.$refs.dataGrid;
      const ajax = new Ajax(
        "https://ej2services.syncfusion.com/production/web-services/api/Orders",
        "GET"
      );
      ajax.send();
      ajax.onSuccess = function(results) {
        // set the ref variable with returned data
        grid.ej2Instances.setProperties({dataSource: JSON.parse(results)});
      }
    }
  }
}
</script>

<style>
  @import url(https://cdn.syncfusion.com/ej2/material.css);
</style>
