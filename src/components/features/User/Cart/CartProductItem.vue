<template>
  <div class="d-flex flex-row justify-content-between px-5 p-2">
    <span>{{ product.title }}</span>
    <span><strong>{{ product.price }}</strong></span>
    <button class="btn btn-danger" @click="deleteProductFromCart">Supprimer</button>
  </div>
</template>

<script>
import { eventBus} from "@/main";

export default {
  name: "CartProductItem",
  props: ['product'],
  methods: {
    deleteProductFromCart() {
      eventBus.deleteProductFromCart({...this.product})
    }
  }
}
</script>

<style scoped>

</style>