<template>
  <div class="d-flex flex-row flex-wrap">
    <shop-product-item v-for="product in products" :product="product" :key="product.id"></shop-product-item>
  </div>
</template>

<script>
import ShopProductItem from "@/components/features/User/Shop/ShopProductItem";

export default {
  name: "ShopProductList",
  components: {
    ShopProductItem,
  },
  props: ['products']
}
</script>

<style scoped>

</style>