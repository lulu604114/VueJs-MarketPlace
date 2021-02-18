<template>
  <div class="d-flex flex-column flex-wrap">
    <cart-product-item v-for="product in cart" :product="product" :key="product.id"></cart-product-item>
    <div v-if="cart.length">TOTAL : {{ totalCart }}</div>
  </div>
</template>

<script>
import CartProductItem from "@/components/features/User/Cart/CartProductItem";

export default {
  name: "CartProductList",
  components: {
    CartProductItem
  },
  props: ['cart'],
  computed: {
    totalCart() {
      return this.cart.reduce((total, product) => {
        total += parseInt(product.price);
        return total;
      }, 0);
    }
  }
}
</script>

<style scoped>

</style>