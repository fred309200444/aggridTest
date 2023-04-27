<script>
import "ag-grid-community/dist/styles/ag-grid.css";
import "ag-grid-community/dist/styles/ag-theme-alpine.css";
import { AgGridVue } from "ag-grid-vue3";
import { reactive, onMounted } from "vue";

export default {
  name: "App",
  components: {
    AgGridVue,
  },
  setup() {
    const columnDefs = reactive({
      value: [
        { headerName: "productName", field: "name", sortable: true },
        { headerName: "Model", field: "model", sortable: true },
        { headerName: "Price", field: "price", sortable: true },
      ],
    });
    const rowData = reactive({
      value: [
        { name: "Toyota", model: "Celica", price: 35000 },
        { name: "Ford", model: "Mondeo", price: 32000 },
        { name: "Porsche", model: "Boxster", price: 72000 },
        { name: "tesla", model: "models", price: 100000 },
        { name: "audi", model: "A1", price: 59000 },
      ],
    });

    return {
      columnDefs,
      rowData,
    };
  },
};
</script>

<template>
  <ag-grid-vue
    style="width: 900px; height: 5000px"
    class="ag-theme-alpine"
    :columnDefs="columnDefs.value"
    :rowData="rowData.value"
    rowSelection="multiple"
    animateRows="true"
  >
  <span>4</span>
  </ag-grid-vue>
  
</template>

<style>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
