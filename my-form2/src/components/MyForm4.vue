<template>
    <h1>College Info</h1>
    <div id="app" class="container mt-5">
  <h1 class="text-center mb-4">College Student Information</h1>
  
  <div class="row">
    <div class="col-md-6" v-for="(student, index) in students" :key="index">
      <div class="card mb-4">
        <div class="card-body">
          <h5 class="card-title">{{ student.name }}</h5>
          <p class="card-text">Age: {{ student.age }}</p>
          <p class="card-text">Major: {{ student.major }}</p>
          <p class="card-text">GPA: {{ student.gpa }}</p>
        </div>
      </div>
    </div>
  </div>
</div>

</template>

<script>
export default {
    data() {
        return {
            students: [
          { name: 'John Doe', age: 20, major: 'Computer Science', gpa: 3.5 },
          { name: 'Jane Smith', age: 21, major: 'Biology', gpa: 3.8 },
          { name: 'David Johnson', age: 19, major: 'History', gpa: 3.2 },
          { name: 'Emily Brown', age: 22, major: 'Mathematics', gpa: 3.9 },
          { name: 'Michael Wilson', age: 20, major: 'Psychology', gpa: 3.6 }                
            ]
        }
    }

}
</script>

<style>

</style>