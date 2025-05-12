<!-- Sidebar.vue -->
<template>
  <div class="sidebar bg-white shadow-sm">
    <div class="sidebar-header p-3 border-bottom">
      <h4 class="mb-0 fw-bold text-primary">Super Admin</h4>
    </div>
    <div class="sidebar-menu p-3">
      <ul class="nav nav-pills flex-column">
        <li class="nav-item mb-2">
          <a href="#" class="nav-link active d-flex align-items-center">
            <i class="bi bi-speedometer2 me-2"></i>Dashboard
          </a>
        </li>
        <li class="nav-item mb-2">
            <a href="#" class="nav-link text-dark d-flex align-items-center">
                <i class="bi bi-people me-2"></i>Users
            </a>
        </li>
        <li class="nav-item mb-2">
          <a href="#" class="nav-link text-dark d-flex align-items-center">
            <i class="bi bi-person me-2"></i>Product
          </a>
        </li>
        <li class="nav-item mb-2">
          <a href="#" class="nav-link text-dark d-flex align-items-center">
            <i class="bi bi-graph-up me-2"></i>Reports
          </a>
        </li>
        <li class="nav-item mb-2">
          <a href="#" class="nav-link text-dark d-flex align-items-center">
            <i class="bi bi-gear me-2"></i>Settings
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Sidebar',
});
</script>

<style scoped>
.sidebar {
  width: 250px;
  min-height: 100vh;
  transition: all 0.3s ease;
  z-index: 1000;
}

.nav-link {
  border-radius: 0.375rem;
  transition: all 0.2s ease;
}

.nav-link:hover {
  background-color: rgba(13, 110, 253, 0.1);
}

.nav-link.active {
  font-weight: 500;
}

@media (max-width: 992px) {
  .sidebar {
    position: fixed;
    left: -250px;
  }
  
  .sidebar.active {
    left: 0;
  }
}
</style>