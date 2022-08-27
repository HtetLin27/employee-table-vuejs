<template>
 <div class="top-bar-box">
   <div class="top-bar">
    <div class="left-topbar">
       <div class="arrow-icon"><i class="fa-solid fa-arrow-left"></i></div>
       <p class="employee-dir">Employee Directory</p>
       <div class="filter-icon"><i class="fa-solid fa-filter"></i></div>
       <div class="search-icon"><i class="fa-solid fa-magnifying-glass"></i></div>
       <div class="edit-icon"><i class="fa-solid fa-pen"></i></div>
    </div>
    <div class="right-topbar">
       <button @click="employeeCreate" class="create-employee">Create Employee</button>
       <i class="fa-solid fa-ellipsis-vertical"></i>
    </div>
   </div>
   <EmployeeTable/>
 </div>
   <div :class="{employeecreating:status}"  >
      <CreateEmployee/>

   </div>
</template>

<script>
import EmployeeTable from './EmployeeTable.vue';
import CreateEmployee from './CreateEmployee.vue';
export default {
  name: "Topbar",
  components: {
    EmployeeTable,
    CreateEmployee
},
data(){
   return{
      status:true
   }
},
 methods:{
   employeeCreate(){
      if(this.status == true){
         this.status = false
         console.log(true)
      }else{
      this.status = true
      console.log(false)}
   }

 }
};
</script>
<style>
 .top-bar-box{
    display: flex;
    flex: 25;
    flex-direction: column;
   
 }
 .top-bar{
    display: flex;
    justify-content: space-between;
    background-color: #cbd6ce;  
 }
 .top-bar i{
    font-size: 20px;
    cursor: pointer;

 }
 .left-topbar{
    display: flex;
    align-items: center;
 }
 .right-topbar{
    display: flex;
    align-items: center;
 }
 .top-bar i:hover{
    color:#4cd137 ;


 }
 .arrow-icon{
    color:#4cd137 ;
    margin-right: 15px;
    margin-left: 15px;
    cursor: pointer;
 }
 .employee-dir{
    margin-right: 50px;
    cursor: pointer;
    font-size: 18px;
 }
 .filter-icon{
    margin-right: 30px;
 }
 .search-icon{
    margin-right: 30px;
 }
 .create-employee{
    padding: 10px;
    border-radius: 5px;
    background-color: #23d990;
    color: #fff;
    margin-left: -320px;
    margin-right: 20px;
    cursor: pointer;
    font-size: 18px;
   font-family: sans-serif;
   border: #23d990;
 }
 .create-employee:hover{
   border:1px solid #badbce;
   color: black;

 }
 .employeecreating{
   display: none;
 }


</style>