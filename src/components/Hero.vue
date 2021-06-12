<template>
  <div class="container">
    <div class="hero">
      <!-- Dekstop -->
      <div class="d-none d-md-block">
        <div class="row mt-4">
          <div class="col-md-6">
            <div class="d-flex h-100">
              <div class="justify-content-center align-self-center">
                <h2>
                  <strong>Lorem ipsum,</strong> <br />
                  atau ringkasnya lipsum
                </h2>
                <p>
                  adalah teks standar yang ditempatkan untuk mendemostrasikan
                  elemen grafis.
                </p>
                <router-link class="btn btn-md btn-deta" to="/produk"
                  ><b-icon-arrow-right></b-icon-arrow-right> Order</router-link
                >
              </div>
            </div>
          </div>
          <div class="col-md-6">
            <img src="../assets/images/hero.png" width="100%" />
          </div>
        </div>
      </div>

      <!-- Hp -->
      <div class="d-sm-block d-md-none">
        <div class="row mt-4 hp">
          <div class="col-md-6 mb-3">
            <img src="../assets/images/hero.png" width="100%" />
          </div>
          <div class="col-md-6">
            <div class="d-flex h-100">
              <div class="justify-content-center align-self-center">
                <h2>
                  <strong>Lorem ipsum,</strong> <br />
                  atau ringkasnya lipsum
                </h2>
                <p>
                  adalah teks standar yang ditempatkan untuk mendemostrasikan
                  elemen grafis.
                </p>
                <router-link class="btn btn-md btn-deta" to="/produk"
                  ><b-icon-arrow-right></b-icon-arrow-right> Order</router-link
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Hero",
};
</script>
<style>
</style> 