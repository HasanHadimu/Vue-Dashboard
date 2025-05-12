<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-primary shadow-sm">
    <div class="container-fluid">
      <a class="navbar-brand fw-bold" href="#">Logo</a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNav"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <div class="d-flex ms-auto align-items-center">
          <!-- Search Bar -->
          <form class="d-flex me-3" role="search">
            <input
              class="form-control form-control-sm"
              type="search"
              placeholder="Search"
              aria-label="Search"
              v-model="searchQuery"
              @keyup.enter="onSearch"
            />
          </form>
          <!-- Profile Dropdown -->
          <div class="dropdown">
            <a
              class="nav-link dropdown-toggle text-white"
              href="#"
              role="button"
              id="profileDropdown"
              data-bs-toggle="dropdown"
              aria-expanded="false"
            >
              <i class="bi bi-person-circle me-1"></i>Profil
            </a>
            <ul class="dropdown-menu dropdown-menu-end" aria-labelledby="profileDropdown">
              <li><a class="dropdown-item" href="#">Lihat Profil</a></li>
              <li><hr class="dropdown-divider"></li>
              <li><a class="dropdown-item" href="#">Logout</a></li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "Navbar",
  setup() {
    const searchQuery = ref("");

    const onSearch = () => {
      console.log("Searching for:", searchQuery.value);
      // Nanti bisa emit event ke parent kalau mau
    };

    return {
      searchQuery,
      onSearch,
    };
  },
});
</script>
