<template>
  <div class="grid">
    <div class="left col">
      <div class="py-2">
        <Button
          @click="active = 0"
          class="p-button-text"
          label="Activate 1st"
        />
        <Button
          @click="active = 1"
          class="p-button-text mr-2"
          label="Activate 2nd"
        />
        <Button
          @click="active = 2"
          class="p-button-text mr-2"
          label="Activate 3rd"
        />
      </div>
    </div>
    <div class="middle col-5">
      <Menu :model="items" />
    </div>
    <div class="right col-18">
      <Breadcrumb :home="home" :model="breadcrumbItems">
        <template #item="{item}">
          <a :href="item.url">{{ item.label }}</a>
        </template>
      </Breadcrumb>
      <div class="flex justify-content-between">
        <h2>SKU</h2>
        <div class="btn-group">
          <Button label="Submit" />
          <Button label="Disabled" disabled="disabled" />
          <SplitButton
            label="Info"
            :model="splitbuttonItems"
            class="p-button-info mb-2"
          ></SplitButton>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Menu from "primevue/menu";
import Button from "primevue/button";
import Breadcrumb from "primevue/breadcrumb";
import SplitButton from "primevue/splitbutton";

export default {
  name: "PageOne",
  components: {
    Menu,
    Button,
    Breadcrumb,
    SplitButton,
  },
  data() {
    return {
      items: [
        {
          label: "Options",
          items: [
            {
              label: "Update",
              icon: "pi pi-refresh",
              command: () => {
                this.$toast.add({
                  severity: "success",
                  summary: "Updated",
                  detail: "Data Updated",
                  life: 3000,
                });
              },
            },
            {
              label: "Delete",
              icon: "pi pi-times",
              command: () => {
                this.$toast.add({
                  severity: "warn",
                  summary: "Delete",
                  detail: "Data Deleted",
                  life: 3000,
                });
              },
            },
          ],
        },
        {
          label: "Navigate",
          items: [
            {
              label: "Vue Website",
              icon: "pi pi-external-link",
              url: "https://vuejs.org/",
            },
            {
              label: "Router",
              icon: "pi pi-upload",
              command: () => {
                window.location.hash = "/fileupload";
              },
            },
          ],
        },
      ],
      breadcrumbItems: [
        { label: "Home" },
        { label: "Dashboard" },
        { label: "Overview" },
      ],
      splitbuttonItems: [
        {
          label: "Update",
          icon: "pi pi-refresh",
          command: () => {},
        },
      ],
    };
  },
};
</script>

<style></style>
