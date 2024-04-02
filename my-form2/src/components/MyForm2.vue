<template>
  <div id="app" class="container mt-5">
    <h1>Consumer Information Form</h1>

    <form @submit.prevent="submitForm">
      <div class="mb-3">
        <label for="name" class="form-label">Name</label>
        <input
          type="text"
          class="form-control"
          id="name"
          v-model="consumer.name"
          :class="{ 'is-invalid': submitted && !consumer.name }"
          required
        />
        <div class="invalid-feedback">Please enter your name.</div>
      </div>
      <div class="mb-3">
        <label for="email" class="form-label">Email address</label>
        <input
          type="email"
          class="form-control"
          id="email"
          v-model="consumer.email"
          :class="{ 'is-invalid': submitted && !emailIsValid }"
          required
        />
        <div class="invalid-feedback">Please enter a valid email address.</div>
      </div>
      <div class="mb-3">
        <label for="age" class="form-label">Age</label>
        <input
          type="number"
          class="form-control"
          id="age"
          v-model.number="consumer.age"
          :class="{ 'is-invalid': submitted && !consumer.age }"
          required
        />
        <div class="invalid-feedback">Please enter your age.</div>
      </div>
      <div class="mb-3">
        <label for="phone" class="form-label">Phone Number</label>
        <input
          type="tel"
          class="form-control"
          id="phone"
          v-model="consumer.phone"
          :class="{ 'is-invalid': submitted && !consumer.phone }"
          required
        />
        <div class="invalid-feedback">Please enter your phone number.</div>
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
      consumer: { name: "", email: "", age: null, phone: "" },
      submitted: false,
    };
  },

  computed: {
    emailIsValid() {
      return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(this.consumer.email);
    },
  },

  methods: {
    submitForm() {
      // Validation check before submission
      if (
        !this.consumer.name ||
        !this.consumer.email ||
        !this.consumer.age ||
        !this.consumer.phone ||
        !this.emailIsValid
      ) {
        this.submitted = true;
        return;
      }

      // Here you can handle form submission, e.g., make an API call to save consumer data
      console.log("Consumer Information:", this.consumer);
      // Simulate submission success
      this.submitted = true;
      // You can reset the form after submission if needed
      // this.consumer = { name: '', email: '', age: null, phone: '' };
    },
  },
};
</script>

<style></style>
