<template>
       <div class="product-card">
          <div class="product-card__img">
            <img :src="product.images[0]" alt="">
          </div>
          <div class="product-card__text-wrapper">
            <a href="#" class="product-card__title">{{ product.title }}</a>
          </div>
        </div>
</template>

<script>
export default {
    props: ["product"],
}
</script>

<style>

</style>