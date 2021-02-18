<template>
  <form class="d-flex flex-column">
    <h4>Ajouter un produit: </h4>
    <hr class="w-100">
    <div class="form-group">
      <label>Image</label>
      <input v-model="form.image" type="text" class="form-control">
    </div>
    <div class="form-group">
      <label>Titre</label>
      <input v-model="form.title" type="text" class="form-control">
    </div>
    <div class="form-group">
      <label>Description</label>
      <textarea v-model="form.description" class="form-control"></textarea>
    </div>
    <div class="form-group">
      <label>Prix</label>
      <input v-model="form.price" type="number" class="form-control">
    </div>
    <ul v-if="errors.length">
      <li class="text-danger" v-for="error in errors" :key="error">{{ error }}</li>
    </ul>
    <button @click="trySubmit" class="btn btn-primary">Ajouter</button>
  </form>
</template>

<script>
import {eventBus} from "@/main";

export default {
  name: "AdminProductForm",
  data() {
    return {
      form: {
        image: '',
        title: '',
        description: '',
        price: 0
      },
      errors: []
    }
  },
  methods: {
    trySubmit(event) {
      event.preventDefault();
      if (this.formIsValid()) {
        eventBus.addProduct({...this.form});
        eventBus.changePage('User');
       }
    },
    formIsValid() {
      this.errors = [];

      if (!this.form.image) {
        this.errors.push('Image required');
      }
      if (!this.form.title) {
        this.errors.push('title required');
      }
      if (!this.form.description) {
        this.errors.push('description required');
      }
      if (!this.form.price) {
        this.errors.push('price required');
      }

      return this.errors.length ? false : true;
    }
  }
}
</script>

<style scoped>

</style>