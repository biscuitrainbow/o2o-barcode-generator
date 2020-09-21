<template>
  <div id="app">
    <!-- <vue-csv-import v-model="products" :map-fields="['name', 'price', 'barcode']"></vue-csv-import> -->

    <div class="flex flex-wrap ">
      <div class="mb-2 p-2 border border-gray-900" v-for="product in products" :key="product.barcode">
        <p class="ml-2">{{product.name}}</p>
        <div class="flex items-center">
          <barcode
            :value="product.barcode"
            :width="1"
            :height="50"
            :fontSize="12"
          >Show this if the rendering fails.</barcode>

          <div class="flex items-baseline">
            <h3 class="text-3xl font-bold mr-1">{{product.price}}</h3>
            <p>Coins</p>
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
      products: [
        { name: "โพสอิทรูปรถบัส Set A", price: "15", barcode: "Stationary_01" },
        { name: "โพสอิทรูปรถบัส Set B", price: "15", barcode: "Stationary_02" },
        {
          name: "โพสอิทรูปทรงสตรอเบอร์รี่",
          price: "15",
          barcode: "Stationary_03",
        },
        { name: "โพสอิทรูปทรงแตงโม", price: "15", barcode: "Stationary_04" },
        {
          name: "โพสอิทชุด Friday รูปแมว สีเขียว",
          price: "25",
          barcode: "Stationary_05",
        },
        {
          name: "โพสอิทชุด Friday รูปกระต่าย สีชมพู",
          price: "25",
          barcode: "Stationary_06",
        },
        {
          name: "โพสอิทชุด Friday รูปแมว สีขาว",
          price: "25",
          barcode: "Stationary_07",
        },
        {
          name: "โพสอิทชุด Finger รูปอีโมจินิ้วมือ",
          price: "15",
          barcode: "Stationary_08",
        },
        { name: "ชุดยางลบมาการอง", price: "25", barcode: "Stationary_09" },
        { name: "ชุดยางลบ Fast Food", price: "29", barcode: "Stationary_10" },
        {
          name: "ชุดยางลบ Sweet Dessert",
          price: "29",
          barcode: "Stationary_11",
        },
        {
          name: "ยางลบแบบแท่ง (เติมไส้ได้)",
          price: "25",
          barcode: "Stationary_12",
        },
        {
          name: "Decoration Tape สีเขียว",
          price: "39",
          barcode: "Stationary_13",
        },
        {
          name: "Decoration Tape แมวสีขาว-ดำ",
          price: "39",
          barcode: "Stationary_14",
        },
        {
          name: "Decoration Tape แมวสีเหลือง",
          price: "39",
          barcode: "Stationary_15",
        },
        {
          name: "Decoration Tape ดาวสีเหลือง",
          price: "39",
          barcode: "Stationary_16",
        },
        {
          name: "Decoration Tape แพนด้าสีขาว",
          price: "39",
          barcode: "Stationary_17",
        },
        {
          name: "Decoration Tape สีชมพู",
          price: "39",
          barcode: "Stationary_18",
        },
        {
          name: "ปากกาหมึกซึมมาริโอ สีเหลือง",
          price: "15",
          barcode: "Stationary_19",
        },
        {
          name: "ปากกาหมึกซึมมาริโอ สีแดง",
          price: "15",
          barcode: "Stationary_20",
        },
        {
          name: "ปากกาหมึกซึมมาริโอ สีเขียว",
          price: "15",
          barcode: "Stationary_21",
        },
        {
          name: "ปากกาหัวเรืองแสง รูปหมี",
          price: "22",
          barcode: "Stationary_22",
        },
        {
          name: "ปากกาหัวเรืองแสง รูปโพนี่",
          price: "22",
          barcode: "Stationary_23",
        },
        {
          name: "ปากกาหัวเรืองแสง รูปยูนิคอร์น",
          price: "22",
          barcode: "Stationary_24",
        },
        {
          name: "ชุดปากกาหลากสี แบบจุดและลาย",
          price: "-",
          barcode: "Stationary_25",
        },
        {
          name: "ชุดปากกาหมึกซึม ลายการ์ตูนน่ารัก",
          price: "-",
          barcode: "Stationary_26",
        },
        { name: "ดินสอแตงโม", price: "-", barcode: "Stationary_27" },
        { name: "ดินสอมะนาว", price: "-", barcode: "Stationary_28" },
        { name: "ดินสอสตรอเบอร์รี่", price: "-", barcode: "Stationary_29" },
        { name: "ดินสอสับปะรด", price: "-", barcode: "Stationary_30" },
        { name: "ดินสอห่านสีฟ้า", price: "-", barcode: "Stationary_31" },
        { name: "สมุดโน๊ต สีขาว ", price: "25", barcode: "Stationary_32" },
        { name: "สมุดโน๊ต สีดำ", price: "25", barcode: "Stationary_33" },
        { name: "สมุดโน๊ต สีฟ้า", price: "25", barcode: "Stationary_34" },
        {
          name: "ชั้นวางเครื่องเขียน M094",
          price: "199",
          barcode: "Stationary_35",
        },
        {
          name: "ชั้นวางเครื่องเขียน M012",
          price: "129",
          barcode: "Stationary_36",
        },
        {
          name: "Sanitary Tools (Self-disinfected) สีฟ้า",
          price: "69",
          barcode: "SanitaryTools_01",
        },
        {
          name: "Sanitary Tools (Self-disinfected) สีชมพู",
          price: "69",
          barcode: "SanitaryTools_02",
        },
        {
          name: "Sanitary Tools (Self-disinfected)  สีเงิน",
          price: "49",
          barcode: "SanitaryTools_03",
        },
        {
          name: "ที่วางโทรศัพท์แบบคล้องคอ สีชมพู",
          price: "59",
          barcode: "Phone-holder_01",
        },
        {
          name: "ที่วางโทรศัพท์แบบคล้องคอ สีดำ",
          price: "59",
          barcode: "Phone-holder_02",
        },
        {
          name: "ที่วางโทรศัพท์แบบคล้องคอ สีฟ้า",
          price: "59",
          barcode: "Phone-holder_03",
        },
        {
          name: "ที่วางโทรศัพท์แบบหนีบหัวเตียง สีฟ้า",
          price: "79",
          barcode: "Phone-holder_04",
        },
        {
          name: "ที่วางโทรศัพท์แบบหนีบหัวเตียง สีชมพู",
          price: "79",
          barcode: "Phone-holder_06",
        },
        { name: "เลย์รสมะนาว 70 g.", price: "49", barcode: "Snack_01" },
        { name: "เลย์รสแตงกวา 70 g.", price: "49", barcode: "Snack_02" },
        { name: "เลย์รสมะเขือเทศ 70 g.", price: "49", barcode: "Snack_03" },
        { name: "เลย์รสบาร์บีคิว 70 g.", price: "49", barcode: "Snack_04" },
        { name: "เลย์รสวาซาบิ 70 g.", price: "49", barcode: "Snack_05" },
        { name: "เลย์รสมะนาว 40 g.", price: "29", barcode: "Snack_06" },
        { name: "เลย์รสวาซาบิ 40 g.", price: "29", barcode: "Snack_07" },
        { name: "เลย์รสแตงกวา 40 g.", price: "29", barcode: "Snack_08" },
        { name: "เลย์รสบาร์บีคิว 40 g.", price: "29", barcode: "Snack_09" },
        { name: "เลย์รสมะเขือเทศ 40 g.", price: "29", barcode: "Snack_10" },
        {
          name: "โอริโอรสชาเขียว ขนาด 97g. X 2",
          price: "129",
          barcode: "Snack_11",
        },
      ],
    };
  },
};
</script>

<style >
.vue-barcode-element {
  /* max-width: 250px; */
}
</style>