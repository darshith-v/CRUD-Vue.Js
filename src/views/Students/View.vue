<template>
  <div>
    <div class="card">
      <div class="card-header">
        <h4>
          Students
          <RouterLink to="/students/create" class="btn btn-primary float-end">
             Add Student
          </RouterLink>
        </h4>
      </div>
      <table class="table table-bordered">
        <thead>
          <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Course</th>
            <th>Email</th>
            <th>Phone</th>
            <th>Created At</th>
            <th>Action</th>
          </tr>
        </thead>
        <tbody>
          <tr>

          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>

import axios from 'axios'

export default {
  name: 'students',
  data() {
    return {
      students: []
    }
  },
  mounted() {
    
    this.getStudents();
    // console.log('i am here')
  }, 
  methods: {
    getStudents() {

      axios.get('http://localhost:8000/api/students').then(res => {
        console.log(res)
      });
    }
  }
}

</script>