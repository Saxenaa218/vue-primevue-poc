<template>
  <div class="main">
    <div class="sidebar">Sidebar</div>
    <div class="container">
      <Breadcrumb :home="home" :model="items" />
      <h1 class="add-new-sku">Add New Sku</h1>
      <Divider />
      <div class="sku-section">
        <div class="sku-article">
          <span class="sku-heading"
            >You are adding new SKU to your existing rows</span
          >
          <span class="sub-heading">
            Sed ut perspiciatis unde omnis iste natus error sit voluptatem
            accusantium doloremque laudantium, totam rem aperiams
          </span>
        </div>
        <div class="adjoining-btn">
          <Button label="Cancel, Go Back" class="btn transparent" />
          <Button label="Save & Add SKU" class="btn colored" />
        </div>
      </div>
      <Divider />
      <div class="row commonRowTopPadding">
        <div class="commonHeadingStyle widthBigColumn">SKU Basic Deals</div>
        <div class="doubleColumn">
          <div>
            <div class="makeRow">
              <label for="username1" class="commonHeadingStyle">sku name</label>
              <InputText
                id="username1"
                type="username"
                aria-describedby="username1-help"
                placeholder="Lorem Ipsum"
              />
              <small id="username1-help"
                >This is a hint text to help user.</small
              >
            </div>
            <div class="makeRow">
              <label for="username1" class="commonHeadingStyle">sku code</label>
              <InputText
                id="username1"
                type="username"
                aria-describedby="username1-help"
                placeholder="Lorem Ipsum"
              />
              <small id="username1-help"
                >This is a hint text to help user.</small
              >
            </div>
          </div>
          <div class="commonHeadingStyle">Serilization Method</div>
          <div class="doubleColumn">
            <div class="field-radiobutton">
              <RadioButton
                id="city2"
                name="city"
                value="Los Angeles"
                v-model="city"
              />
              <label for="city2">A-Los Angeles</label>
            </div>
            <div class="field-radiobutton">
              <RadioButton
                id="city2"
                name="city"
                value="Los Angeles"
                v-model="city"
              />
              <label for="city2">B-Los Angeles</label>
            </div>
          </div>
          <div class="doubleColumn">
            <div class="field-radiobutton">
              <RadioButton
                id="city2"
                name="city"
                value="Los Angeles"
                v-model="city"
              />
              <label for="city2">C-Los Angeles</label>
            </div>
            <div class="field-radiobutton">
              <RadioButton
                id="city2"
                name="city"
                value="Los Angeles"
                v-model="city"
              />
              <label for="city2">D-Los Angeles</label>
            </div>
          </div>
          <div class="commonHeadingStyle">Magnitude</div>
          <div class="doubleColumn">
            <InputText type="text" value="5" />
            <Dropdown
              value="Liter"
              :virtualScrollerOptions="{ itemSize: 38 }"
              placeholder="Liter"
            ></Dropdown>
          </div>
          <div class="commonHeadingStyle">Defaut Expiry</div>
          <div class="doubleColumn">
            <InputText type="text" value="5" />
            <Dropdown
              :virtualScrollerOptions="{ itemSize: 38 }"
              placeholder="Days"
            ></Dropdown>
          </div>
          <div class="commonHeadingStyle doubleColumn">
            <p><span>Click to upload </span>or drag and drop</p>
            <p>SVG, PNG, JPG or GIF (max. 800x400px)</p>
          </div>
        </div>
      </div>
      <Divider />
      <div class="row commonRowTopPadding">
        <div class="commonHeadingStyle widthBigColumn">Manufacturing Config</div>
        <div class="doubleColumn">
          <h4 class="commonHeadingStyle">
            Select the attributes that are to be recorded while activating this
            SKU
          </h4>
          <div>
            <div class="field-checkbox">
              <Checkbox
                id="city1"
                name="city"
                value="Chicago"
                v-model="cities"
              />
              <label for="city1">MRP</label>
            </div>
            <div class="field-checkbox">
              <Checkbox
                id="city1"
                name="city"
                value="Chicago"
                v-model="cities"
              />
              <label for="city1">Manufacturing Date</label>
            </div>
            <div class="field-checkbox">
              <Checkbox
                id="city1"
                name="city"
                value="Chicago"
                v-model="cities"
              />
              <label for="city1">Production Order Number</label>
            </div>
          </div>
          <div>
            <div class="field-checkbox">
              <Checkbox
                id="city1"
                name="city"
                value="Chicago"
                v-model="cities"
              />
              <label for="city1">Batch No</label>
            </div>
            <div class="field-checkbox">
              <Checkbox
                id="city1"
                name="city"
                value="Chicago"
                v-model="cities"
              />
              <label for="city1">Expiry Date</label>
            </div>
          </div>
          <div class="sku-facility-map doubleColumn">
            <h4 class="commonHeadingStyle">
              SKU to Facility Mapping (Where can this SKU be manufactured?)
            </h4>
            <MultiSelect
              v-model="selectedCities2"
              :options="cities"
              optionLabel="name"
              placeholder="Select Cities"
              display="chip"
            />
            <h6>This is a hint text to help user.</h6>
            <h4>INFO: This product is manufactured in 10 facilities</h4>
          </div>
        </div>
      </div>
      <Divider />
      <div class="row commonRowTopPadding">
        <div class="commonHeadingStyle widthBigColumn">Packaging Level</div>
        <div>
          <div>
            <Dropdown
              :virtualScrollerOptions="{ itemSize: 38 }"
              placeholder="L2"
            ></Dropdown>
            <h6>This is a hint text to help user.</h6>
            <h4 class="commonHeadingStyle">SKU Constraints</h4>
            <div class="field-radiobutton">
              <RadioButton
                id="city2"
                name="city"
                value="Los Angeles"
                v-model="city"
              />
              <label for="city2">Yes</label>
            </div>
            <div class="field-radiobutton">
              <RadioButton
                id="city3"
                name="city"
                value="New York"
                v-model="city"
              />
              <label for="city3">No</label>
            </div>
            <h4 class="commonHeadingStyle">SKU Constraints</h4>
            <div>
              <Dropdown
                v-model="selectedItem1"
                :options="items"
                optionLabel="label"
                optionValue="value"
                :virtualScrollerOptions="{ itemSize: 38 }"
                placeholder="Creme 200 gm"
              ></Dropdown>
              <InputText type="text" value="10" />
            </div>
            <div>
              <Dropdown
                v-model="selectedItem1"
                :options="items"
                optionLabel="label"
                optionValue="value"
                :virtualScrollerOptions="{ itemSize: 38 }"
                placeholder="Creme 200 gm"
              ></Dropdown>
              <InputText type="text" value="10" />
            </div>
            <h4 class="commonHeadingStyle">+ Add More</h4>
            <h4 class="commonHeadingStyle">
              INFO: In this packaging you are putting 10 qty of creme 200 gm and
              20 qty of creme 100 gm
            </h4>
          </div>
        </div>
      </div>
      <Divider />
      <div class="row commonRowTopPadding">
        <div class="widthBigColumn">Original4Sure Config</div>
        <div>
          <div class="makeRow">
            <label for="username1" class="commonHeadingStyle"
              >A consumer scans the product for the first time</label
            >
            <InputText
              id="username1"
              type="username"
              aria-describedby="username1-help"
            />
            <small id="username1-help">This is a hint text to help user.</small>
          </div>
          <div class="makeRow">
            <label for="username1" class="commonHeadingStyle"
              >Same consumer scans it for the second or subsequent time</label
            >
            <InputText
              id="username1"
              type="username"
              aria-describedby="username1-help"
            />
            <small id="username1-help">This is a hint text to help user.</small>
          </div>
          <div class="makeRow">
            <label for="username1" class="commonHeadingStyle">Username</label>
            <InputText
              id="username1"
              type="username"
              aria-describedby="username1-help"
            />
            <small id="username1-help">This is a hint text to help user.</small>
          </div>
          <div class="makeRow">
            <label for="username1" class="commonHeadingStyle"
              >A different consumer scans an already scanned product</label
            >
            <InputText
              id="username1"
              type="username"
              aria-describedby="username1-help"
            />
            <small id="username1-help">This is a hint text to help user.</small>
          </div>
        </div>
      </div>
      <Divider />

      <div class="row commonRowTopPadding">
        <div class="commonHeadingStyle widthBigColumn">Trade Promotion Config</div>
        <div>
          <h4 class="commonHeadingStyle">Team member</h4>
          <div class="makeRow">
            <label for="username1" class="commonHeadingStyle">sku name</label>
            <InputText
              id="username1"
              type="username"
              aria-describedby="username1-help"
              placeholder="Lorem Ipsum"
            />
            <small id="username1-help">This is a hint text to help user.</small>
          </div>
        </div>
      </div>
      <Divider />
      <div class="row commonRowTopPadding">
        <div class="commonHeadingStyle widthBigColumn">Learn more</div>
        <div class="adjoining-btn">
          <Button label="Cancel, Go Back" class="btn transparent" />
          <Button label="Save & Add SKU" class="btn colored" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Breadcrumb from "primevue/breadcrumb";
import Button from "primevue/button";
import Divider from "primevue/divider";
import RadioButton from "primevue/radiobutton";
import Checkbox from "primevue/checkbox";
import InputText from "primevue/inputtext";
import Dropdown from "primevue/dropdown";
import MultiSelect from "primevue/multiselect";
export default {
  components: {
    Breadcrumb,
    Button,
    Divider,
    RadioButton,
    Checkbox,
    InputText,
    Dropdown,
    MultiSelect,
  },
  props: {
    msg: String,
  },
  data() {
    return {
      home: {
        icon: "pi pi-home",
        to: "/",
      },
      items: [
        { label: "Computer" },
        { label: "Notebook" },
        { label: "Accessories" },
        { label: "Backpacks" },
        { label: "Item" },
      ],
      city: "",
      selectedCities2: [
        { name: "New York", code: "NY" },
        { name: "Rome", code: "RM" },
      ],
      cities: [
        { name: "New York", code: "NY" },
        { name: "Rome", code: "RM" },
        { name: "London", code: "LDN" },
        { name: "Istanbul", code: "IST" },
        { name: "Paris", code: "PRS" },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src="./mystyles.css">
</style>
