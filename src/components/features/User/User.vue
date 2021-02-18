<template>
  <div class="d-flex flex-row">
    <shop class="w-75"></shop>
    <cart class="w-25"></cart>
  </div>
</template>

<script>
import Shop from "@/components/features/User/Shop/Shop";
import Cart from "@/components/features/User/Cart/Cart";

export default {
  name: "User",
  components: {
    Shop,
    Cart
  }
}
</script>

<style scoped>

</style>