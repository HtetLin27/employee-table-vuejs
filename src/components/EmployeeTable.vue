<template>
  <table >
  <tr>
    <th>Employee</th>
    <th>Location</th>
    <th>Email</th>
    <th>Phone</th>
    <th>Employee Code</th>
    <th>Custom Tags</th>
  </tr>
  <tr v-for = "item in employeelist" :key = "item.id">
    <td>{{item.name}}</td>
    <td>{{item.email}}</td>
    <td>{{item.office}}</td>
    <td>{{item.department}}</td>
    <td>{{item.empCode}}</td>
    <td>{{item.position}}</td>
  </tr>
</table>

</template>

<script>

import axios from 'axios'
export default {
  name: "EmployeeTable",
  data(){
    return{
      employeelist:[]
    }
  },
  async mounted(){
    const result = await axios.get('http://localhost:3000/employeelist');
    console.log(result);
    this.employeelist = result.data;
  }

};
</script>
<style>

</style>