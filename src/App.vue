<template>
  <div class="app-container">
    <Navbar @toggle-sidebar="toggleSidebar" />
    <div class="app-layout">
      <Sidebar :isActive="sidebarActive" @close-sidebar="closeSidebar" />
      <main class="main-content" :class="{ 'sidebar-collapsed': !sidebarActive }">
        <div class="content-container">
          <DataTable />
        </div>
      </main>
      <div v-if="sidebarActive" class="sidebar-overlay" @click="closeSidebar"></div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted, onBeforeUnmount } from 'vue';
import Navbar from './components/Navbar.vue';
import Sidebar from './components/Sidebar.vue';
import DataTable from './views/Home.vue';

import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-icons/font/bootstrap-icons.css'
import './style.css';

export default defineComponent({
  name: 'App',
  components: {
    Navbar,
    Sidebar,
    DataTable,
  },
  setup() {
    const sidebarActive = ref(true);
    const isMobile = ref(false);

    const checkScreenSize = () => {
      isMobile.value = window.innerWidth < 992;
      if (isMobile.value) {
        sidebarActive.value = false;
      } else {
        sidebarActive.value = true;
      }
    };

    onMounted(() => {
      checkScreenSize();
      window.addEventListener('resize', checkScreenSize);
    });

    onBeforeUnmount(() => {
      window.removeEventListener('resize', checkScreenSize);
    });

    const toggleSidebar = () => {
      sidebarActive.value = !sidebarActive.value;
    };

    const closeSidebar = () => {
      if (isMobile.value) {
        sidebarActive.value = false;
      }
    };

    return {
      sidebarActive,
      toggleSidebar,
      closeSidebar,
    };
  },
});
</script>

<style scoped>
.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.app-layout {
  display: flex;
  flex: 1;
  position: relative;
}

.main-content {
  flex: 1;
  padding: 1.5rem;
  background-color: #f8f9fa;
  transition: margin-left 0.3s ease;
  margin-left: 250px; /* Default sidebar width */
}

.main-content.sidebar-collapsed {
  margin-left: 0;
}

.content-container {
  background-color: white;
  border-radius: 0.5rem;
  padding: 1.5rem;
  box-shadow: 0 0.125rem 0.25rem rgba(0, 0, 0, 0.075);
}

.sidebar-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 100;
  display: none;
}

@media (max-width: 992px) {
  .main-content {
    margin-left: 0;
  }
  
  .sidebar-overlay {
    display: block;
  }
}

@media (max-width: 768px) {
  .main-content {
    padding: 1rem;
  }
}
</style>