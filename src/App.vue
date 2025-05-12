<template>
  <div class="app-container">
    <Navbar />
    <div class="app-layout">
      <Sidebar />
      <main class="main-content">
        <div class="content-container">
          <DataTable />
        </div>
      </main>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Navbar from './components/Navbar.vue';
import Sidebar from './components/Sidebar.vue';
import DataTable from './views/Home.vue';

import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-icons/font/bootstrap-icons.css'

export default defineComponent({
  name: 'App',
  components: {
    Navbar,
    Sidebar,
    DataTable,
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
}

.main-content {
  flex: 1;
  padding: 1.5rem;
  background-color: #f8f9fa;
  transition: margin-left 0.3s ease;
}

.content-container {
  background-color: white;
  border-radius: 0.5rem;
  padding: 1.5rem;
  box-shadow: 0 0.125rem 0.25rem rgba(0, 0, 0, 0.075);
}

@media (max-width: 992px) {
  .main-content {
    margin-left: 0;
  }
}
</style>