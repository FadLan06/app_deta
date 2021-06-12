<template>
  <div id="app">
    <Navbar />
    <Hero />
    <div class="container">
      <div class="row mt-5">
        <div class="col-md">
          <h2>Best <strong>Produk</strong></h2>
        </div>
        <div class="col-md">
          <router-link to="/produk" class="btn btn-deta btn-sm float-right"
            ><b-icon-eye></b-icon-eye> Lihat Semua</router-link
          >
        </div>
      </div>

      <div class="row mb-4">
        <div
          class="col-md-4 mt-4"
          v-for="product in products"
          :key="product.id"
        >
          <BProduk :product="product" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import Hero from "@/components/Hero.vue";
import BProduk from "@/components/BProduk.vue";
import axios from "axios";

export default {
  name: "Home",
  components: {
    Navbar,
    Hero,
    BProduk,
  },
  data() {
    return {
      products: [],
    };
  },
  methods: {
    setProducts(data) {
      this.products = data;
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/best-products")
      .then((response) => this.setProducts(response.data))
      .catch((error) => console.log(error));
  },
};
</script>
