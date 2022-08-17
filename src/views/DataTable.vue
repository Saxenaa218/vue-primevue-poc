<template>
  <div>
    <DataTable :value="products">
      <template #empty>
        No customers found.
      </template>
      <template #loading>
        Loading customers data. Please wait.
      </template>
      <Column selectionMode="multiple" headerStyle="width: 3rem"></Column>
      <Column field="image" header="Image"></Column>
      <Column field="code" header="Code"></Column>
      <Column field="name" header="Name"></Column>
      <Column field="mrp" header="MRP(₹)"></Column>
      <Column field="packagingLevel" header="Packaging Level"></Column>
      <Column field="createdOn" header="Created On"></Column>
    </DataTable>
  </div>
</template>

<script>
import DataTable from "primevue/datatable";
import Column from "primevue/column";

export default {
  name: "DataTableVue",
  components: {
    DataTable,
    Column,
  },
  data() {
    return {
      products: [
        {
          id: "1000",
          image: "bamboo-watch.jpg",
          code: "f230fh0g3",
          name: "Bamboo Watch",
          mrp: 65,
          packagingLevel: "INSTOCK",
          createdOn: "Product Description",
        },
        {
          id: "1001",
          image: "black-watch.jpg",
          code: "nvklal433",
          name: "Black Watch",
          mrp: 72,
          packagingLevel: "INSTOCK",
          createdOn: "Product Description",
        },
        {
          id: "1002",
          image: "blue-band.jpg",
          code: "zz21cz3c1",
          name: "Blue Band",
          mrp: 79,
          packagingLevel: "LOWSTOCK",
          createdOn: "Product Description",
        },
        {
          id: "1003",
          image: "blue-t-shirt.jpg",
          code: "244wgerg2",
          name: "Blue T-Shirt",
          mrp: 29,
          packagingLevel: "INSTOCK",
          createdOn: "Product Description",
        },
      ],
    };
  },
};
</script>
