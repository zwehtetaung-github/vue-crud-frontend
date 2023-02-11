<template>
  <div class="row justify-content-center">
    <div class="col-md-6">
      <h3 class="text-center">Update Student</h3>
        <form @submit.prevent="handleUpdateForm">
            <div class="form-group">
                <label for="name">Name</label>
                <input type="text" id="name" class="form-control mb-2" v-model="student.name" placeholder="Enter name" required>
            </div>

            <div class="form-group">
                <label for="email">Email</label>
                <input type="email" id="email" class="form-control mb-2" v-model="student.email" placeholder="Enter email" required>
            </div>

            <div class="form-group">
                <label for="phone">Phone</label>
                <input type="text" id="phone" class="form-control mb-2" v-model="student.phone" placeholder="Enter phone" required>
            </div>

            <div class="form-group">
                <button class="btn btn-primary btn-block">Update</button>
            </div>
        </form>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            student: {}
        }
    },
    created() {
      let apiURL = `http://localhost:8000/students/${this.$route.params.id}`;

      axios.get(apiURL).then((res) => {
        this.student = res.data;
      });
    },
    methods: {
      handleUpdateForm() {
        let apiURL = `http://localhost:8000/students/update-student/${this.$route.params.id}`;

        axios.put(apiURL, this.student).then((res) => {
          console.log(res);
          this.$router.push('/view');
        }).catch(error => {
          console.log(error);
        });
      }
    }
}
</script>

<style>

</style>