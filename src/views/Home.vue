<template>
  <MultiSelect
    v-model="selectedSKU"
    :options="list"
    optionLabel="name"
    optionValue="code"
    dataKey="code"
  >
    <template #value="slotProps">
      <template v-if="!slotProps.value || slotProps.value.length === 0">
        Select SKUs
      </template>
      <template v-else>
        <div class="multiselect-placeholder">
          <template
            v-if="
              (slotProps.value && slotProps.value.length) === skuList.length
            "
          >
            All SKUs
          </template>
          <template v-else>
            <template v-if="(slotProps.value && slotProps.value.length) >= 1">
              {{ slotProps.value.length }} SKUs Selected
            </template>
          </template>
        </div>
      </template>
    </template>
  </MultiSelect>
</template>

<script>
// @ is an alias to /src
import MultiSelect from "primevue/multiselect";
import data from "./../data";
export default {
  name: "Home",
  data() {
    return {
      list: data,
      selectedSKU: undefined,
    };
  },
  components: {
    MultiSelect,
  },
};
</script>
