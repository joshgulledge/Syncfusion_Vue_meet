<template>
  <div id="app">

   <!-- after we import syncfusion we can use the ejs-grid tag -->
   <ejs-grid 
    :dataSource="data">

     <!-- to customize the columns -->
     <e-columns>
       <!-- include the column sub tab -->

       <e-column 
        field="OrderID"
        headerText="Order Id" 
        textAlign="Right">
       </e-column>

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
import { DataManager, WebApiAdaptor } from '@syncfusion/ej2-data';


Vue.use(GridPlugin);
export default {
  // temp hardcode some data to be displayed in the grid
  data () {
    return {
     data: new DataManager({
       url: "https://ej2services.syncfusion.com/production/web-services/api/Orders?$top=7",
       adaptor: new WebApiAdaptor()
     })
    }
  }
}
</script>

<style>
  @import url(https://cdn.syncfusion.com/ej2/material.css);
</style>
