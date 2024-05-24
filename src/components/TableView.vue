<template>
    <table>
        <th v-for="(heading, index) in headings" :key="index">{{ heading }}</th>
        <tbody>
            <tr v-for="employee in employees" :key="employee.EmployeeId">
        <td><input disabled type="text" v-model="employee.EmployeeId"/></td>
        <td><input type="text" v-model="employee.FirstName" /></td>
        <td><input type="text" v-model="employee.LastName" /></td>
        <td><input type="text" v-model="employee.DOB"/></td>
        <td><input type="text" v-model="employee.Salary"/></td>
        <td><input type="text" v-model="employee.Address"/></td>
        <td><button @click="editEmploye">edit</button><button @click="deleteEmploye(employee.EmployeeId)">delete</button></td>
      </tr>
      <tr v-if="showEdit">
        <td><input type="text" v-model="newEmployee.EmployeeId"></td>
       <td><input type="text" v-model="newEmployee.FirstName"></td>
       <td><input type="text" v-model="newEmployee.LastName"></td>
       <td><input type="text" v-model="newEmployee.DOB"></td>
       <td><input type="text" v-model="newEmployee.Salary"></td>
       <td><input type="text" v-model="newEmployee.Address"></td>
      </tr>
        </tbody>
    </table>
    <button @click="addEmployee"> add </button>
    <button @click="save">save</button>
</template>

<script>
export default {
  name: 'TableView',
  props: {
    headings: Array,
    employees: Array
  },
  methods: {
    addEmployee() {
      this.showEdit = !this.showEdit;
      if(this.showEdit) {
        this.newEmployee ={
          EmployeeId: '',
        FirstName: '',
        LastName: '',
        DOB: '',
        Salary: '',
        Address: ''
        }
      }
    },
    deleteEmploye(id) {
      this.$emit('delete-Employe', id)
    },
    editEmploye() {
      
      this.$emit('editEmploye', this.newEmployee)
    },
    save() {
      console.log('save')
      this.showEdit = false;
      this.$emit('save-Employe', this.newEmployee)
    }
  },
  data() {
    return {
      showEdit: false,
      newEmployee: {
        EmployeeId: '',
        FirstName: '',
        LastName: '',
        DOB: '',
        Salary: '',
        Address: ''
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
