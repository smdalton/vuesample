<template>

  <div id="app" class="small-container">
    <h1>Employees All </h1>
    <employee-form @add:employee="addEmployee" @cat:message="catMessageAlert" />
    <employee-table :employees="employees" />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import EmployeeTable from '@/components/EmployeeTable.vue'
import EmployeeForm from '@/components/EmployeeForm.vue'
export default {
  name: 'App',
  components: {
    EmployeeTable,
    EmployeeForm,
  },
  data() {
    return {
      employees: [
        {
          id: 1,
          name: 'Frodo baggins',
          email: 'ringbearer@mordorexcursions.com'
        },
        {
          id: 2,
          name: 'Gandalf the Grey',
          email: 'gandalf@icandomagic.com'
        },
        {
          id: 3,
          name: 'Samwise',
          email: 'sam@ringsupport.com'
        },
      ],
    }
  },
  methods: {
    addEmployee(employee) {
      const lastId =
        this.employees.length > 0 ? 
        this.employees[this.employees.length -1].id : 0;
        const id = lastId + 1;
        const newEmployee = { ...employee, id};
      
      this.employees = [...this.employees, newEmployee]
      console.log(this.employees)
    },
    catMessageAlert(){
      alert('Mew Mew fish time')
    },
  },
}
</script>

<style>
button {
    background: #009435;
    border: 1px solid #009435;
  }

  .small-container {
    max-width: 680px;
  }
</style>
