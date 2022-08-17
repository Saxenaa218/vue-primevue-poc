<template>
  <div>
    <Breadcrumb :home="home" :model="items" />
  </div>
</template>

<script>
import Breadcrumb from "primevue/breadcrumb";
export default {
  components: {
    Breadcrumb,
  },
  name: "BreadCrumb",
  data() {
    return {
      home: {
        icon: "pi pi-home",
        to: "/",
      },
      items: [{ label: "Dashboard" }, { label: "Overview" }],
    };
  },
};
</script>
