<template>
  <div>
    <h3 class="p-3 border-bottom">Shopping</h3>
    <shop-product-list :products="products" class="p-3"></shop-product-list>
  </div>
</template>

<script>
import ShopProductList from "@/components/features/User/Shop/ShopProductList";
import {eventBus} from "@/main";

export default {
  name: "Shop",
  components: {
    ShopProductList,
  },
  data() {
    return {
      products: []
    }
  },
  created() {
    this.products = eventBus.products;
    eventBus.$on('update:product', (products) => {
      this.products = products;
    })
  }
}
</script>

<style scoped>

</style>