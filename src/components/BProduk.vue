<template>
  <!-- <h2>{{ product.nama }}</h2> -->
  <div class="card shadow card-product">
    <img
      :src="'assets/images/' + product.gambar"
      class="card-img-top"
      alt="..."
    />
    <div class="card-body">
      <h6 class="card-title">
        <strong>{{ product.nama }}</strong>
      </h6>
      <p class="card-text">Harga : Rp. {{ product.harga }}</p>
      <router-link :to="'/produk/' + product.id" class="btn btn-deta btn-sm"
        ><b-icon-cart></b-icon-cart> Pesan</router-link
      >
      <!-- <router-link
        :to="'/produk/' + product.id"
        class="btn btn-success btn-sm float-right"
        ><b-icon-eye></b-icon-eye> Lihat</router-link
      > -->
    </div>
  </div>
</template>
<script>
export default {
  name: "BProduk",
  props: ["product"],
};
</script>
<style lang="">
</style>