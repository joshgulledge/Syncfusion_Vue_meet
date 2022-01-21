<template>
  <div id="app">

   <!-- after we import syncfusion we can use the ejs-grid tag -->
   <!-- after you allow paging, define settings in the pagesettings under data -->
   <!-- add the properties here for the page to actually use them -->
   <ejs-grid 
    :dataSource="localData"
    :allowPaging="true"
    :pageSettings=pageSettings
    :allowSorting="true"
    :allowFiltering="true"
    :editSettings="editOptions"
    :toolbar="toolbarOptions">

     <!-- to customize the columns -->
     <e-columns>
       <!-- include the column sub tab -->
       <e-column 
        field="_id"
        headerText="Order Id" 
        textAlign="Right"
        :isPrimaryKey="true">
        <!-- the headerText is what is displayed, while field is the name of data field -->
       </e-column>

       <e-column 
        field="name"
        headerText="Customer Name" 
        textAlign="Right">
       </e-column>

       <e-column 
        field="company"
        headerText="Company Name" 
        textAlign="Right"
        editType="dropdownedit">
       </e-column>

       <e-column 
        field="balance"
        headerText="Price Ordered" 
        textAlign="Right"
        format="C2">
       </e-column>
      <!-- the format of c2 displays value in dollars -->
     </e-columns>

   </ejs-grid>

  </div>
</template>

<script>

// imports
import Vue from 'vue';
import { GridPlugin, Page, 
          Sort, Filter, Edit, Toolbar } from '@syncfusion/ej2-vue-grids';


Vue.use(GridPlugin);
export default {
  // temp hardcode some data to be displayed in the grid
  data () {
    return {
      localData: [
        {
          "_id": "61e89cf9ebd0ac2158c6befc",
          "balance": "$2,106.24",
          "name": "Rosetta Day",
          "company": "CYTRAK",
          "email": "rosettaday@cytrak.com",
          "phone": "+1 (819) 599-2533",
          "address": "370 Nolans Lane, Worcester, West Virginia, 5594"
        },
        {
          "_id": "61e89cf9d7e72b106011732a",
          "balance": "$3,696.02",
          "name": "Corina Reese",
          "company": "SPLINX",
          "email": "corinareese@splinx.com",
          "phone": "+1 (887) 556-2145",
          "address": "204 Allen Avenue, Century, Washington, 6982"
        },
        {
          "_id": "61e89cf9a26252b2f29883b0",
          "balance": "$3,079.43",
          "name": "June Byrd",
          "company": "SNORUS",
          "email": "junebyrd@snorus.com",
          "phone": "+1 (923) 557-3764",
          "address": "954 Rose Street, Carbonville, Arizona, 6893"
        },
        {
          "_id": "61e89cf9121b6459bc714736",
          "balance": "$3,724.74",
          "name": "Estella Barton",
          "company": "AQUAMATE",
          "email": "estellabarton@aquamate.com",
          "phone": "+1 (998) 474-2076",
          "address": "875 Whitwell Place, Verdi, Oklahoma, 2888"
        },
        {
          "_id": "61e89cf9f67e47f192ed5f42",
          "balance": "$1,903.40",
          "name": "Sawyer Henson",
          "company": "EXOSWITCH",
          "email": "sawyerhenson@exoswitch.com",
          "phone": "+1 (939) 591-3148",
          "address": "307 Vanderbilt Street, Vicksburg, Federated States Of Micronesia, 6379"
        },
        {
          "_id": "61e89cf95f736a6e83d702aa",
          "balance": "$3,059.02",
          "name": "Sadie Walls",
          "company": "EXOZENT",
          "email": "sadiewalls@exozent.com",
          "phone": "+1 (832) 429-3034",
          "address": "214 Tapscott Avenue, Bedias, New Hampshire, 1225"
        },
        {
          "_id": "61e89cf94999cd599c3934cb",
          "balance": "$3,460.72",
          "name": "Guthrie Cantu",
          "company": "BOVIS",
          "email": "guthriecantu@bovis.com",
          "phone": "+1 (841) 558-2085",
          "address": "443 Clymer Street, Winston, Tennessee, 7904"
        },
        {
          "_id": "61e89cf9b89877c688d901a8",
          "balance": "$2,465.39",
          "name": "Sosa Moses",
          "company": "KIDSTOCK",
          "email": "sosamoses@kidstock.com",
          "phone": "+1 (913) 576-2395",
          "address": "661 Livonia Avenue, Sehili, Kentucky, 8833"
        },
        {
          "_id": "61e89cf9edcffb736aac3e18",
          "balance": "$3,271.80",
          "name": "Lelia Roth",
          "company": "BIFLEX",
          "email": "leliaroth@biflex.com",
          "phone": "+1 (904) 521-3315",
          "address": "188 Polhemus Place, Gambrills, New Mexico, 6923"
        },
        {
          "_id": "61e89cf95c55cd01f5f956b4",
          "balance": "$2,024.57",
          "name": "Julianne Booker",
          "company": "ZIDOX",
          "email": "juliannebooker@zidox.com",
          "phone": "+1 (880) 553-3936",
          "address": "239 Eckford Street, Saticoy, Georgia, 7910"
        },
        {
          "_id": "61e8a04ba5099751ea4c27de",
          "balance": "$2,138.35",
          "name": "Josefa Riley",
          "company": "STROZEN",
          "email": "josefariley@strozen.com",
          "phone": "+1 (896) 543-3992",
          "address": "283 Bowne Street, Dante, Virginia, 7538"
        },
        {
          "_id": "61e8a04b0a82fe73abeaaf06",
          "balance": "$1,907.43",
          "name": "Ofelia Blevins",
          "company": "FRANSCENE",
          "email": "ofeliablevins@franscene.com",
          "phone": "+1 (980) 417-3412",
          "address": "561 Garfield Place, Sabillasville, Minnesota, 7326"
        },
        {
          "_id": "61e8a04b9363c2b40e4674b5",
          "balance": "$1,098.69",
          "name": "Adele Bowers",
          "company": "COMBOGENE",
          "email": "adelebowers@combogene.com",
          "phone": "+1 (862) 452-2714",
          "address": "842 Hamilton Walk, Flintville, Vermont, 901"
        },
        {
          "_id": "61e8a04b81a4528459264b91",
          "balance": "$2,657.85",
          "name": "Lucinda Hensley",
          "company": "NAMEBOX",
          "email": "lucindahensley@namebox.com",
          "phone": "+1 (985) 592-2227",
          "address": "355 Kane Street, Alafaya, Iowa, 8537"
        },
        {
          "_id": "61e8a04bfe9884f7a11f0f9d",
          "balance": "$3,545.72",
          "name": "Gentry Levy",
          "company": "NORSUL",
          "email": "gentrylevy@norsul.com",
          "phone": "+1 (977) 444-2955",
          "address": "520 Lester Court, Lorraine, Ohio, 1997"
        }
      ],
      // below are the settings used to define syncfusion options, add to the column for options to be used
      pageSettings: {
        pageSize: 5
      },
      editOptions: {
        allowAdding: true,
        allowEditing: true,
        allowDeleting: true,
        mode: "Dialog" // this brings up a dialog box to make edits in
        // you can use "Batch" as a mode to save multiple options at same time
        // you can use "Normal" as a mode to save single line option

      },
      toolbarOptions: ["Add", "Edit", "Delete", "Update", "Cancel"],
      numericParams: {
        params: {
          format: "C2"
        }
      }
    }
  },
  // add the page and sort and filter property from syncfusion
  provide: {
    grid: [
      Page,
      Sort,
      Filter, 
      Edit,
      Toolbar
    ]
  }
}
</script>

<style>
  @import url(https://cdn.syncfusion.com/ej2/material.css);
</style>
