<template>
    <TableView :headings="headings" :employees="employees" @save-Employe = "handleSave" @delete-Employe="handleDelete"></TableView>
</template>

<script>
import TableView from "./TableView.vue"

export default {
  name: 'HelloWorld',
  props: {
    headings: Array,
    employees: Array
  },
  components: {
    TableView
  },
  methods: {
    editEmploye() {
      console.log('hi')
    }, 
    handleSave(employe) {
      this.$emit('employe-save', employe)
    },
    handleDelete(employe) {
      this.$emit('employe-delete', employe)
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
