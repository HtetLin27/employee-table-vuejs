<template>
 <div class="table-box">
  <table class=" table table-striped table-hover" >
    <thead class="table-head">
      <tr>
        <th><input type="checkbox" class="check-box success"/>Employee</th>
        <th>Location</th>
        <th>Email</th>
        <th>Phone</th>
        <th>Department</th>
        <th>Employee Code</th>
        <th>Custom Tags</th>
      </tr>
    </thead>
    <tbody class="table-body">
        <tr v-for = "item in employeelist" :key = "item.id">
          <td class="name-box"> <input type="checkbox"  class="check-box primary"> <img :src=item.userImg alt="userImg" class="employeeProfile">{{item.name}}</td>
          <td>{{item.office}}</td>
          <td>{{item.email}}</td>
          <td>{{item.phone}}</td>
          <td>
            <select class="select" >
              <option selcected>{{item.department}}</option>
              <option value="Product Department">Product Department</option>
              <option value="Development" >Development</option>
              <option value="Tech & Development" >Tech & Development</option>
              <option value="Customer Success" >Customer Success</option>
              <option value="Human Resource Managing Department">Human Resource Managing Department</option>
              <option value="Marketing Management">Marketing Management</option>
            </select>
          </td>
          <td>{{item.empCode}}</td>
          <td>{{item.position}}</td>
        </tr>
        
    </tbody>
  </table>
 </div>
 
</template>

<script>

import axios from 'axios'
export default {
  name: "EmployeeTable",
  data(){
    return{
      employeelist:[],
      check:"checked"
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
.table-box{
 width: 100%;
 height: 600px;
 overflow-y: scroll;
 cursor: pointer;
 font-size: 14px;
}
.table-head{
  border-top: 1px solid lightgray;
  border-bottom: 1px solid lightgray;
  position:sticky;
  top:0;
}
.table-head::after{
  content: '';
  width: 100%;
  height: 100%;
  position: absolute;
  bottom: 0;
  left: 0;
  background-color:#b5e2d0;
  z-index: -1;
}
.employeeProfile{
  width: 30px;
  height: 30px;
  border-radius: 50%;
  margin-right: 10px;
}
.check-box{
  margin-right: 20px;
}
.name-box{
  box-shadow: 10px -1px 8px 0px rgba(0,0,0,0.5);
}

.select{
  outline: none;
  border: none;
  background-color: inherit;
  cursor: pointer;
  width:180px
}

input[type=checkbox]{
  accent-color: #23d990;
  background-color: #fff;
}
/* input[type=checkbox]::before{
  content: "\2714";
  position: absolute;
  top: -2px;
  border: 0.1em solid #000;
  display: inline-block;
  border-radius: 0.2em;
  padding-left: 0.2em;
  padding-bottom:0.3em ;
  width: 1em;
  height: 1em;
  color: transparent;
  vertical-align: bottom;

}
input[type=checkbox]:checked::before{
  background-color: mediumseagreen;
  border-color: mediumseagreen;
  color: #fff;
} */
</style>

<!-- UNICODEU+02212
HEX CODE&#x2212;
HTML CODE&#8722;
HTML ENTITY&minus;
CSS CODE\2212 -->

<!-- UNICODEU+02714
HEX CODE&#x2714;
HTML CODE&#10004;
HTML ENTITY—
CSS CODE\2714 -->