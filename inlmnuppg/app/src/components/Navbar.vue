<template>
  <!-- Navbar -->
  <nav class="navbar navbar-expand-lg navbar-light bg-info">
    <!-- Container wrapper -->
    <div class="container">
      <!-- Toggle button -->
      <button
        class="navbar-toggler"
        type="button"
        data-mdb-toggle="collapse"
        data-mdb-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <i class="fas fa-bars"></i>
      </button>

      <!-- Collapsible wrapper -->
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <!-- Navbar brand -->
        <router-link class="navbar-brand mt-2 mt-lg-0" to="/">
          <i class="fa-brands fa-shopware me-2"></i> Shopware.se
        </router-link>
        <!-- Left links -->
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <router-link class="nav-link" to="/">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/products">Products</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/about">About Us</router-link>
          </li>
        </ul>
        <!-- Left links -->
      </div>
      <!-- Collapsible wrapper -->

      <!-- Right elements -->
      <div class="d-flex align-items-center">


        <!-- Notifications -->
        <div class="dropdown">
          <a
            class="text-reset me-3 dropdown-toggle hidden-arrow"
            href="#"
            id="navbarDropdownMenuLink"
            role="button"
            data-mdb-toggle="dropdown"
            aria-expanded="false"
          >
            <i class="fas fa-shopping-cart"></i>
            <span v-if="cartItemCount" class="badge rounded-pill badge-notification bg-danger">{{cartItemCount}}</span>
          </a>
          <div
            class="dropdown-menu dropdown-menu-end shopping-cart"
            aria-labelledby="navbarDropdownMenuLink"
          >
            <ShoppingCart />
          </div>
        </div>
      </div>  
      <!-- Right elements -->
    </div>
    <!-- Container wrapper -->
  </nav>
<!-- Navbar -->
</template>

<script>
import { mapGetters } from 'vuex'
import ShoppingCart from './shoppingCart/ShoppingCart.vue'
export default {
  components: { ShoppingCart },
  name: 'PrimaryNavigation',
  computed: {
    ...mapGetters(['cartItemCount'])
  },
  methods: {
  }
}
</script>

<style scoped>
  .shopping-cart {
    min-width: 450px;
  }
</style>