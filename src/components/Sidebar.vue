<template>
  <div :class="['sidebar bg-white shadow-sm', { active: isActive }]">
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
  props: {
    isActive: Boolean
  },
  emits: ['close-sidebar']
});
</script>

<style scoped>
.sidebar {
  width: 250px;
  background: #fff;
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  z-index: 101;
  transition: transform 0.3s ease;
  box-shadow: 2px 0 5px rgba(0,0,0,0.1);
}

@media (max-width: 992px) {
  .sidebar {
    transform: translateX(-100%);
  }
  
  .sidebar.active {
    transform: translateX(0);
  }
}
</style>
