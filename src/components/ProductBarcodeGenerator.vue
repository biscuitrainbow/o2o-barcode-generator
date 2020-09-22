<template>
  <div>
    <div class="px-4 py-4">
      <vue-csv-import
        v-if="products.length == 0"
        v-model="products"
        :map-fields="['name','category', 'pricePerUnit','unit', 'barcode']"
        autoMatchFields="true"
        headers="true"
        table-class="mt-4"
        button-class="text-white bg-primary px-4 py-1 mt-4"
      ></vue-csv-import>
    </div>

    <div class="flex mb-4 no-print">
      <div class="mr-4" v-for="category in categories" :key="category">
        <div class="flex items-center">
          <input
            :id="category"
            v-model="selectedCategories"
            name="selected-categories"
            type="checkbox"
            :value="category"
            class="mr-1"
          />
          <label :for="category">{{category}}</label>
        </div>
      </div>
    </div>

    <div class="grid grid-cols-2">
      <div
        class="mb-4 mx-1 border border-gray-600 product-item normal-size"
        style
        v-for="product in selectedCategoriesProducts"
        :key="product.barcode"
      >
        <div class="flex justify-between items-center text-white bg-primary p-2">
          <div>
            <p class="text-md">{{product.name.trim()}}</p>
            <p class="text-xs">{{product.category.trim()}}</p>
          </div>

          <img class="w-12 h-12" src="@/assets/images/o2o_logo_white.png" alt srcset />
        </div>

        <div class="flex justify-between items-center mt-4 px-2">
          <barcode
            class="mr-2"
            :value="product.barcode"
            :width="1"
            :height="60"
            :fontSize="12"
          >Show this if the rendering fails.</barcode>

          <div class="text-primary capitalize">
            <div class="flex items-baseline">
              <h3 class="text-3xl font-medium mr-1">{{product.pricePerUnit}}</h3>
              <p class="text-xs">Coins</p>
            </div>
            <p class="text-xs text-gray-900 mr-3">per {{product.unit}}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { VueCsvImport } from "vue-csv-import";
import VueBarcode from "vue-barcode";
export default {
  components: { VueCsvImport, barcode: VueBarcode },
  data() {
    return {
      products: [],
      size: "small",
      selectedCategories: [],
    };
  },
  computed: {
    categories() {
      return new Set(this.products.map((product) => product.category));
    },
    selectedCategoriesProducts() {
      return this.products.filter((product) =>
        this.selectedCategories.includes(product.category)
      );
    },
  },
  watch: {
    categories(newValue) {
      this.selectedCategories = Array.from(
        new Set(this.products.map((product) => product.category))
      );
    },
  },
};
</script>

<style >
.product-item:nth-child(10n + 0),
.product-item:nth-child(10n - 1) {
  margin-bottom: 102px;
}

.normal-size {
  min-width: 350px;
  max-width: 350px;
  min-height: 175px;
}

.small-size {
  min-width: 250px;
  max-width: 250px;
  min-height: 175px;
}

* {
  font-family: "Kanit", sans-serif;
  -webkit-print-color-adjust: exact;
}

@media print {
  .no-print,
  .no-print * {
    display: none !important;
  }
}
</style>