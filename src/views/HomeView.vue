<template>
  <div class="products">
    <div class="container">
      <h2 class="products__title">Products</h2>
      <div class="products__wrapper">
        <product-card v-for="item in products" :key="item" :product="item"></product-card>
        <product-card v-for="item in products" :key="item" :product="item"></product-card>
      </div>
    </div>
  </div>
</template>

<script>
import ProductCard from '@/components/ProductCard.vue';
export default {
  components: {ProductCard},
  data() {
    return {
      baseUrl: "https://api.escuelajs.co/api/v1",
      products: [],
    }
  },
  methods: {
    getProducts() {
      fetch(this.baseUrl + "/products?offset=0&limit=5").then(res => res.json())
      .then(data => {
        this.products = data;
      });
    }
  },
  mounted() {
    this.getProducts()
  },
};
</script>
<style lang="sass" scoped>

</style>
<!-- mounted data,computed,method 
data bish malumotlar olib aylantirib ishati
method da xodisalardi ishati
mounted da vasifasi java scripteki dom bilan ishash!!!!! 

-->