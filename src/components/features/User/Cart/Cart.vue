<template>
  <div class="border-left">
    <h3 class="p-3 border-bottom">Panier</h3>
    <cart-product-list :cart="cart"></cart-product-list>
  </div>
</template>

<script>
import CartProductList from "@/components/features/User/Cart/CartProductList";
import { eventBus } from "@/main";

export default {
  name: "Cart",
  components: {
    CartProductList
  },
  data() {
    return {
      cart: []
    }
  },
  created() {
    this.cart = eventBus.cart;
    eventBus.$on('update:cart', (cart) => {
      this.cart = cart;
    })
  }
}
</script>

<style scoped>

</style>