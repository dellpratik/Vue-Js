<template>
  <div id="app" class="container mt-5">
    <h1>Employee Information Form</h1>

    <form @submit.prevent="submitForm">
      <div class="mb-3">
        <label for="name" class="form-label">Name</label>
        <input
          type="text"
          class="form-control"
          id="name"
          v-model="employee.name"
          required
        />
      </div>
      <div class="mb-3">
        <label for="email" class="form-label">Email address</label>
        <input
          type="email"
          class="form-control"
          id="email"
          v-model="employee.email"
          required
        />
      </div>
      <div class="mb-3">
        <label for="department" class="form-label">Department</label>
        <input
          type="text"
          class="form-control"
          id="department"
          v-model="employee.department"
          required
        />
      </div>
      <div class="mb-3">
        <label for="position" class="form-label">Position</label>
        <input
          type="text"
          class="form-control"
          id="position"
          v-model="employee.position"
          required
        />
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>

    <div v-if="submitted" class="alert alert-success mt-3" role="alert">
      Employee information submitted successfully!
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      employee: {
        name: "",
        email: "",
        department: "",
        position: "",
      },
      submitted: false
    };
  },
  methods: {
    submitForm() {
        console.log('Employee Information:', this.employee);
        this.submitted = true;
    }            
  }
};
</script>

<style>
</style>