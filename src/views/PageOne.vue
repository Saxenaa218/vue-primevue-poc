<template>
  <div class="grid">
    <div class="left col-1 ">
      <div
        class="py-2 flex justify-content-between align-items-center flex-column"
      >
        <Button icon="pi pi-home" class="p-button-text m-2" />
        <Button icon="pi pi-search" class="p-button-text m-2" />
        <Button icon="pi pi-search" class="p-button-text m-2" />
        <Button icon="pi pi-search" class="p-button-text m-2" />
        <Button icon="pi pi-search" class="p-button-text m-2" />
        <Button icon="pi pi-users" class="p-button-text m-2" />
        <Button icon="pi pi-search" class="p-button-text m-2" />
      </div>
      <div>
        <Button icon="pi pi-search" class="p-button-text m-2" />
        <Button icon="pi pi-cog" class="p-button-text m-2" />
        <Avatar
          image="https://www.primefaces.org/wp-content/uploads/2020/05/placeholder.png"
          shape="circle"
          class="m-2"
        />
      </div>
    </div>
    <div class="middle col-2">
      <div class="flex justify-content-between align-items-center">
        <h3>
          Onboarding
        </h3>
        <span
          ><Button icon="pi pi-align-right" class="p-button-text p-button-sm"
        /></span>
      </div>
      <Menu :model="items" />
    </div>
    <div class="right col-9">
      <BreadcrumbVue />
      <div class="flex justify-content-between align-items-center">
        <h2>SKU</h2>
        <div class="btn-group">
          <Button
            label="Add Cluster"
            icon="pi pi-box"
            class="p-button-outlined mr-12px p-button-sm"
          />
          <Button
            label="Export"
            disabled="disabled"
            icon="pi pi-cloud-upload"
            class="p-button-outlined mr-12px p-button-sm"
          />
          <SplitButton
            label="Add New SKU"
            :model="splitbuttonItems"
            class="p-button-info p-button-sm"
          ></SplitButton>
        </div>
      </div>
      <div class="flex justify-content-between align-items-center">
        <SelectButton
          v-model="selectButtonValue"
          :options="paymentOptions"
          optionLabel="name"
          optionValue="value"
        />
        <div class="flex justify-content-end align-items-center">
          <Chip label="L1" class="mr-8px h-2rem" removable />
          <Chip label="Date" class="mr-12px h-2rem" removable />
          <Button
            label="Filters"
            icon="pi pi-filter"
            class="p-button-outlined mr-12px p-button-sm"
          />
          <Button icon="pi pi-search" class="p-button-outlined p-button-sm" />
        </div>
      </div>
      <div class="my-4">
        <DataTableVue />
      </div>
      <div>
        <PaginatorVue />
      </div>
    </div>
  </div>
</template>

<script>
import Menu from "primevue/menu";
import Button from "primevue/button";
import SplitButton from "primevue/splitbutton";
import SelectButton from "primevue/selectbutton";
import Chip from "primevue/chip";
// import Paginator from "primevue/paginator";
import Avatar from "primevue/avatar";

import BreadcrumbVue from "./BreadCrumb.vue";
import DataTableVue from "./DataTable.vue";
import PaginatorVue from "./Paginator.vue";

export default {
  name: "PageOne",
  components: {
    Menu,
    Button,
    BreadcrumbVue,
    SplitButton,
    SelectButton,
    Chip,
    DataTableVue,
    PaginatorVue,
    Avatar,
  },
  data() {
    return {
      selectButtonValue: 2,
      items: [
        {
          label: "Facility",
          icon: "pi pi-refresh",
          command: () => {},
        },
        {
          label: "SKU",
          icon: "pi pi-bell",
          command: () => {},
        },
        {
          label: "Ship to party",
          icon: "pi pi-times",
          command: () => {},
        },
        {
          label: "Beneficiary",
          icon: "pi pi-star",
          command: () => {},
        },
        {
          label: "Partner",
          icon: "pi pi-clock",
          command: () => {},
        },
      ],
      splitbuttonItems: [
        {
          label: "Update",
          icon: "pi pi-refresh",
          command: () => {},
        },
      ],
      paymentOptions: [
        { name: "All SKU", value: 1 },
        { name: "Deactived SKU", value: 2 },
        { name: "SKU Cluster", value: 3 },
      ],
    };
  },
};
</script>

<style scoped lang="scss">
.mr-12px {
  margin-right: 12px;
}
.mr-8px {
  margin-right: 8px;
}

/deep/ .pi-times-circle:before {
  // content: "\e946";
  // content: url(https://www.notion.so/icons/rocket_gray.svg?mode=light);
  content: url(../assets/close.svg);
  // font-size: ;
}

/deep/ .pi-filter:before {
  content: url(../assets/filters.svg);
}
</style>
