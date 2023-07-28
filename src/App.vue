<script >
import { TreeViewComponent } from "@syncfusion/ej2-vue-navigations";
import { DataManager, Query, ODataV4Adaptor } from "@syncfusion/ej2-data";
export default {
  components: {
    "ejs-treeview": TreeViewComponent
  },
  data() {
    return {

      fields: { dataSource: data, id: "nodeId", text: "nodeText", child: "nodeChild" }
      // remote binding
      // fields: {
      //   dataSource: remotedata, query: new Query().from('Employees').select('EmployeeID,FirstName,Title').take(5), id: 'EmployeeID', text: 'FirstName', hasChildren: 'EmployeeID',
      //   child: { dataSource: remotedata, query: new Query().from('Orders').select('OrderID,EmployeeID,ShipName').take(5), id: 'OrderID', parentID: 'EmployeeID', text: 'ShipName' }
      // }
    }
  }
}
//remote binding data source
// var remotedata = new DataManager({
//   url: 'https://services.odata.org/V4/Northwind/Northwind.svc',
//   adaptor: new ODataV4Adaptor,
//   crossDomain: true,
// })
var data = [
  {
    nodeId: '01', nodeText: 'Music',
    nodeChild: [
      { nodeId: '01-01', nodeText: 'Gouttes.mp3' }
    ]
  },
  {
    nodeId: '02', nodeText: 'Videos', expanded: true,
    nodeChild: [
      { nodeId: '02-01', nodeText: 'Naturals.mp4' },
      { nodeId: '02-02', nodeText: 'Wild.mpeg' },
    ]
  },
  {
    nodeId: '03', nodeText: 'Documents',
    nodeChild: [
      { nodeId: '03-01', nodeText: 'Environment Pollution.docx' },
      { nodeId: '03-02', nodeText: 'Global Water, Sanitation, & Hygiene.docx' },
      { nodeId: '03-03', nodeText: 'Global Warming.ppt' },
      { nodeId: '03-04', nodeText: 'Social Network.pdf' },
      { nodeId: '03-05', nodeText: 'Youth Empowerment.pdf' },
    ]
  },
]

</script>

<template>
  <ejs-treeview id='treeview' :fields='fields' :showCheckBox="true" :allowEditing="true"
                              :allowDragAndDrop="true" :allowMultiSelection="true"></ejs-treeview>
</template>

<style >
@import "../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../node_modules/@syncfusion/ej2-inputs/styles/material.css";
@import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-navigations/styles/material.css";
@import "../node_modules/@syncfusion/ej2-navigations/styles/material.css";
</style>



