<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a href="" class="navbar-brand">
      <img  class="logo" src="../assets/logo.png" alt="logo.png"> MYSHOPI
    </a>
    <button class="navbar-toggler">
      <span class="navbar-toggler icon"></span>
    </button>
    <div class="collapse navbar-collapse">
      <ul class="navbar-nav">
        <li class="nav-item">
          <a href="#" class="nav-link" @click.prevent="changePage('User')" :class="{active: currentPage === 'User'}">Boutique</a>
        </li>
        <li class="nav-item">
          <a href="#" class="nav-link" @click.prevent="changePage('Admin')" :class="{active: currentPage === 'Admin'}">Admin</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
import {eventBus} from "@/main";

export default {
  name: "TheHeader",
  props: ['currentPage'],
  methods: {
    changePage(page) {
      eventBus.changePage(page);
    }
  }
}
</script>

<style scoped>
.logo {
  width: 30px;
  height: 30px;
}
</style>