<template>
  <div id="app">
    <Navbar />
    <div class="container">
      <!-- <div class="row mt-4">
        <div class="col">
          <h2>Detail <strong>Produk</strong></h2>
          {{ $route.params.id }}
        </div>
      </div> -->

      <div class="row mt-4">
        <div class="col">
          <nav aria-label="breadcrumb">
            <ol class="breadcrumb">
              <li class="breadcrumb-item">
                <router-link to="/" class="text-dark">Home</router-link>
              </li>
              <li class="breadcrumb-item">
                <router-link to="/produk" class="text-dark">Produk</router-link>
              </li>
              <li class="breadcrumb-item active" aria-current="page">Detail</li>
            </ol>
          </nav>
        </div>
      </div>

      <div class="row">
        <div class="col-md-6 mt-2">
          <img
            :src="'../assets/images/' + product.gambar"
            class="img-fluid shadow"
            alt="..."
          />
        </div>
        <div class="col-md-6 mt-2">
          <h3>
            <strong>{{ product.nama }}</strong>
          </h3>
          <hr />
          <h4>
            Harga : Rp.
            <strong style="font-size: 40px"> {{ product.harga }}</strong>
          </h4>
          <hr />
          <form class="mt-4" v-on:submit.prevent>
            <div class="form-group">
              <label for="">Jumlah Pesan</label>
              <input
                type="number"
                class="form-control"
                min="1"
                v-model="pesan.jumlah_pemesanan"
              />
            </div>
            <div class="form-group">
              <label for="">Keterangan</label>
              <textarea
                v-model="pesan.keterangan"
                class="form-control"
              ></textarea>
            </div>
            <button type="submit" class="btn btn-deta" @click="pemesanan">
              <b-icon-cart></b-icon-cart> Pesan
            </button>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Navbar from "@/components/Navbar.vue";
import axios from "axios";
export default {
  name: "Detail",
  components: {
    Navbar,
  },
  data() {
    return {
      product: {},
      pesan: {},
    };
  },
  methods: {
    setProduct(data) {
      this.product = data;
    },
    pemesanan() {
      if (this.pesan.jumlah_pemesanan) {
        this.pesan.products = this.product;
        axios
          .post("http://localhost:3000/keranjangs", this.pesan)
          .then(() => {
            this.$router.push({ path: "/keranjang" });
            this.$toast.success("Sukses Masuk Keranjang", {
              type: "success",
              position: "top-right",
              duration: 3000,
              dismissible: true,
            });
          })
          .catch((err) => console.log(err));
      } else {
        this.$toast.error("Jumlah Pesanan Harus diisi", {
          type: "error",
          position: "top-right",
          duration: 3000,
          dismissible: true,
        });
      }
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/products/" + this.$route.params.id)
      .then((response) => this.setProduct(response.data))
      .catch((error) => console.log(error));
  },
};
</script>
<style>
</style>