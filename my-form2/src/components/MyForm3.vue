<template>
    <h1>Another One</h1>

    <div id="app" class="container mt-5">
  <h1>Consumer Information Form</h1>
  
  <form @submit.prevent="submitForm">
    <div class="mb-3">
      <label for="name" class="form-label">Name</label>
      <input type="text" class="form-control" id="name" v-model="consumer.name" >
      <div v-if="formErrors.name" class="text-danger">{{ formErrors.name }}</div>
    </div>
    <div class="mb-3">
      <label for="address" class="form-label">Address</label>
      <input type="text" class="form-control" id="address" v-model="consumer.address" >
      <div v-if="formErrors.address" class="text-danger">{{ formErrors.address }}</div>
    </div>
    <div class="mb-3">
      <label for="city" class="form-label">City</label>
      <input type="text" class="form-control" id="city" v-model="consumer.city" >
      <div v-if="formErrors.city" class="text-danger">{{ formErrors.city }}</div>
    </div>
    <div class="mb-3">
      <label for="postalCode" class="form-label">Postal Code</label>
      <input type="text" class="form-control" id="postalCode" v-model="consumer.postalCode" >
      <div v-if="formErrors.postalCode" class="text-danger">{{ formErrors.postalCode }}</div>
    </div>
    <div class="mb-3">
      <label for="sex" class="form-label">Sex</label>
      <select class="form-select" id="sex" v-model="consumer.sex" required>
        <option value="">Select</option>
        <option value="male">Male</option>
        <option value="female">Female</option>
      </select>
      <div v-if="formErrors.sex" class="text-danger">{{ formErrors.sex }}</div>
    </div>
    <button type="submit" class="btn btn-primary">Submit</button>
  </form>

  <div v-if="submitted" class="alert alert-success mt-3" role="alert">
    Consumer information submitted successfully!
  </div>
</div>

</template>

<script>
export default {
    data() {
        return {
            consumer: {name:'', address:'', city:'', postalCode:'',sex:''},
            formErrors: {},
            submitted: false
        }
    },
    methods: {
        submitForm() {

        this.formErrors = {}; // Reset form errors
        let valid = true;

        // Validate form fields
        if (!this.consumer.name) {
          this.formErrors.name = 'Name is required';
          console.log(this.formErrors);
          valid = false;
        }
        if (!this.consumer.address) {
          this.formErrors.address = 'Address is required';
          valid = false;
        }
        if (!this.consumer.city) {
          this.formErrors.city = 'City is required';
          valid = false;
        }
        if (!this.consumer.postalCode) {
          this.formErrors.postalCode = 'Postal Code is required';
          valid = false;
        }
        if (!this.consumer.sex) {
          this.formErrors.sex = 'Sex is required';
          valid = false;
        }


        // Submit form if valid
        if (valid) {
          // Here you can handle form submission, e.g., make an API call to save consumer data
          console.log('Consumer Information:', this.consumer);
          // Simulate submission success
          this.submitted = true;
          // You can reset the form after submission if needed
          // this.consumer = { name: '', address: '', city: '', postalCode: '', sex: '' };
        }


        }
    }

}
</script>

<style>

</style>