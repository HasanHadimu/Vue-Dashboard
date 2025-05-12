<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-white shadow-sm">
    <div class="container-fluid">
      <!-- Sidebar Toggle Button (only mobile) -->
      <button
        class="btn btn-outline-dark d-lg-none me-2"
        @click="$emit('toggle-sidebar')"
      >
        <i class="bi bi-list"></i>
      </button>

      <!-- Logo -->
      <a class="navbar-brand fw-bold text-dark" href="#">Logo</a>

      <!-- Navbar Collapse for links (optional links in future) -->
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
              class="nav-link dropdown-toggle text-dark"
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
  emits: ['toggle-sidebar'],
  setup() {
    const searchQuery = ref("");

    const onSearch = () => {
      console.log("Searching for:", searchQuery.value);
    };

    return {
      searchQuery,
      onSearch,
    };
  },
});
</script>
