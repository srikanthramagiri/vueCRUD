<template>
  <Employe :employees="employeesData" :headings="headings" @employe-save="handleSave" @employe-delete= "handleDelete"/>
  
</template>

<script>
import Employe from './components/Employe.vue'

export default {
  name: 'App',
  components: {
    Employe
  },
  data() {
    return {
      employeesData: {},
      headings: ['Employee ID', 'First Name', 'Last Name', 'DOB', 'Salary', 'Address', 'action']
    };
  },
  mounted() {
    // Assign the imported JSON data to the component's data
    this.employeesData = [
        {
          "EmployeeId": 1,
          "FirstName": "John",
          "LastName": "Doe",
          "DOB": "1990-05-15",
          "Salary": 50000,
          "Address": "123 Main St, Cityville"
        },
        {
          "EmployeeId": 2,
          "FirstName": "Jane",
          "LastName": "Smith",
          "DOB": "1985-10-20",
          "Salary": 60000,
          "Address": "456 Elm St, Townburg"
        },
        {
          "EmployeeId": 3,
          "FirstName": "Michael",
          "LastName": "Johnson",
          "DOB": "1978-03-12",
          "Salary": 70000,
          "Address": "789 Oak St, Villageton"
        },
        {
          "EmployeeId": 4,
          "FirstName": "Emily",
          "LastName": "Williams",
          "DOB": "1995-08-25",
          "Salary": 55000,
          "Address": "101 Pine St, Hamletown"
        },
        {
          "EmployeeId": 5,
          "FirstName": "David",
          "LastName": "Brown",
          "DOB": "1982-12-05",
          "Salary": 65000,
          "Address": "202 Maple St, Townsville"
        },
        {
          "EmployeeId": 6,
          "FirstName": "Sarah",
          "LastName": "Jones",
          "DOB": "1993-06-30",
          "Salary": 75000,
          "Address": "303 Cedar St, Villagetown"
        },
        {
          "EmployeeId": 7,
          "FirstName": "Matthew",
          "LastName": "Garcia",
          "DOB": "1989-04-18",
          "Salary": 52000,
          "Address": "404 Birch St, Citytown"
        },
        {
          "EmployeeId": 8,
          "FirstName": "Jessica",
          "LastName": "Martinez",
          "DOB": "1976-09-10",
          "Salary": 80000,
          "Address": "505 Walnut St, Townville"
        },
        {
          "EmployeeId": 9,
          "FirstName": "Christopher",
          "LastName": "Anderson",
          "DOB": "1980-02-28",
          "Salary": 60000,
          "Address": "606 Cherry St, Villageburg"
        },
        {
          "EmployeeId": 10,
          "FirstName": "Amanda",
          "LastName": "Taylor",
          "DOB": "1991-11-08",
          "Salary": 70000,
          "Address": "707 Peach St, Cityburg"
        }
      ];
  }, 
  methods: {
    addEmployee() {

    },
    handleSave(employe) {
     this.employeesData.push(employe)
    }, 
    handleDelete(id) {
      console.log('sadff')
      this.employeesData = this.employeesData.filter(item => item.EmployeeId !== id)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
