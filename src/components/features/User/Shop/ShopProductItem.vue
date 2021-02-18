<template>
  <div class="w-25 p-3">
    <div class="card">
      <img :src="product.img" class="card-img-top p-3" alt="...">
      <div class="card-body">
        <h5 class="card-title">{{ product.title }}</h5>
        <p class="card-text">{{ product.description }}</p>
        <button href="#" class="btn btn-primary" @click="addProductToCart">{{ product.price }}</button>
      </div>
    </div>
  </div>
</template>

<script>
import { eventBus } from "@/main";

export default {
  name: "ShopProductItem",
  props: ['product'],
  methods: {
    addProductToCart() {
      eventBus.addProductToCart({...this.product})
    }
  }
}
</script>

<style scoped>
.product-container {
  height: 200px;
}
</style>