<!-- DataTable.vue -->
<template>
  <div>
    <div class="d-flex justify-content-between align-items-center mb-4">
      <h2 class="mb-0 fw-bold">User Data</h2>
      <button class="btn btn-primary">
        <i class="bi bi-plus-lg me-1"></i>Add User
      </button>
    </div>
    
    <div class="table-responsive rounded-3 shadow-sm">
      <table class="table table-hover align-middle mb-0 bg-white">
        <thead class="bg-light">
          <tr>
            <th class="fw-semibold">First Name</th>
            <th class="fw-semibold">Last Name</th>
            <th class="fw-semibold">Age</th>
            <th class="fw-semibold">Actions</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(item, index) in items" :key="index">
            <td>
              <div class="d-flex align-items-center">
                <div class="ms-3">
                  <p class="fw-bold mb-0">{{ item.first_name }}</p>
                </div>
              </div>
            </td>
            <td>
              <p class="mb-0">{{ item.last_name }}</p>
            </td>
            <td>
              <span class="badge bg-primary rounded-pill">{{ item.age }}</span>
            </td>
            <td>
              <button class="btn btn-sm btn-outline-primary me-2">
                <i class="bi bi-pencil-square"></i>
              </button>
              <button class="btn btn-sm btn-outline-danger">
                <i class="bi bi-trash"></i>
              </button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    
    <nav class="mt-4">
      <ul class="pagination justify-content-center">
        <li class="page-item disabled">
          <a class="page-link" href="#" tabindex="-1">Previous</a>
        </li>
        <li class="page-item active"><a class="page-link" href="#">1</a></li>
        <li class="page-item"><a class="page-link" href="#">2</a></li>
        <li class="page-item"><a class="page-link" href="#">3</a></li>
        <li class="page-item">
          <a class="page-link" href="#">Next</a>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'DataTable',

  setup() {
    const items = ref([
      { age: 40, first_name: 'Dickerson', last_name: 'Macdonald' },
      { age: 21, first_name: 'Larsen', last_name: 'Shaw' },
      { age: 89, first_name: 'Geneva', last_name: 'Wilson' },
      { age: 38, first_name: 'Jami', last_name: 'Carney' }
    ]);

    return { items };
  }
});
</script>

<style scoped>
.table th, .table td {
  padding: 1rem;
}

.table-hover tbody tr:hover {
  background-color: rgba(13, 110, 253, 0.05);
}
</style>