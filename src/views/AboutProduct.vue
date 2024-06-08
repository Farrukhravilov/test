<template>
  <div class="about-product">
    <div class="container">
        <div class="about-product__img-wrapper">
            <div class="about-product__img">
                <img :src="detail.images[mainImgIndex]" alt="">
            </div>
            <ul class="about-product__thumbs">
                <li class="about-product__thumbs-item" v-for="(item, i) in detail.images" :key="item" @click="mainImgIndex = i">
                    <img :src="item" alt="">
                </li>
            </ul>
        </div>
        <div class="about-product__text-wrappe">
            <h2 class="about-product__title">
                {{ detail.title }}
            </h2>
            <p class="about-product__desc">
                {{ detail.description }}
            </p>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    data() {
        return{
            baseUrl: "https://api.escuelajs.co/api/v1",
            detail: {},
            mainImgIndex: 0,
        };
    },
    methods: {
        getDetailProduct() {
            fetch(this.baseUrl + "/products/" + this.$route.params.id)
            .then((res) => res.json())
            .then((data) => {
                this.detail = data;
            });
        },
    },
    mounted(){
        this.getDetailProduct()
    }
};
</script>

<style lang="sss" scoped>

</style>