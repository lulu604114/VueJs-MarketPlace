<template>
  <div class="d-flex flex-row justify-content-center p-5">
    <admin-product-form class="w-50 border p-5"></admin-product-form>
  </div>
</template>

<script>
import AdminProductForm from "@/components/features/Admin/AdminProductForm";
export default {
  name: "Admin",
  components: {
    AdminProductForm
  }
}
</script>

<style scoped>

</style>