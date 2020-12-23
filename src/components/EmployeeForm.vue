<template>
  <div id="employee-form">
      <!-- Event Handler for form submissions, inject database calls at it's definition -->
    <form @submit.prevent="handleSubmit">
      <label>Employee name</label>
      <input v-model="employee.name" type="text" />
      <label>Employee Email</label>
      <input v-model="employee.email" type="text" />
      <button>Add Employee</button>
    </form>
    <button @click="catMessage">The cat says:</button>
  </div>
</template>

<script>
  export default {
    name: 'employee-form',
    data() {
      return {
        employee: {
          name: '',
          email: '',
        },
      }
    },
    methods: {
// TODO: do post/get here when database is integrated
    handleSubmit() {
      this.$emit('add:employee', this.employee)
      },
      catMessage() {
        this.$emit('cat:message')
      },
    },
  }
</script>

<style scoped>
  form {
    margin-bottom: 2rem;
  }
</style>