<template>
  <div>
    <Paginator
      v-model:first="first"
      :rows="1"
      :totalRecords="totalRecords2"
      template="FirstPageLink PrevPageLink CurrentPageReport NextPageLink LastPageLink"
    >
      <template #start>
        <Button
          type="button"
          icon="pi pi-arrow-left"
          label="Previous"
          class="p-button-outlined p-button-sm"
        />
      </template>
      <template #end>
        <Button
          type="button"
          icon="pi pi-arrow-right"
          label="Next"
          iconPos="right"
          class="p-button-outlined p-button-sm"
        />
      </template>
    </Paginator>
  </div>
</template>

<script>
import Paginator from "primevue/paginator";
import Button from "primevue/button";
export default {
  name: "PaginatorVue",
  components: {
    Paginator,
    Button,
  },
  data() {
    return {
      first: 0,
      totalRecords: 120,
      totalRecords2: 12,
    };
  },
  methods: {
    reset() {
      this.first = 0;
    },
  },
};
</script>

<style scoped>
.image-gallery {
  text-align: center;
  padding: 1rem;
}
</style>
