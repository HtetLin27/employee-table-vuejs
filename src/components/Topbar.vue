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
       <button class="create-employee">Create Employee</button>
       <i class="fa-solid fa-ellipsis-vertical"></i>
    </div>
</div>
<EmployeeTable/>
</div>
</template>

<script>
import EmployeeTable from './EmployeeTable.vue';
export default {
  name: "Topbar",
  components: {
    EmployeeTable

    
   
},
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
    background-color: #1bd32b;
    color: #fff;
    margin-left: -300px;
    margin-right: 20px;
    cursor: pointer;
    font-size: 18px;
 }

</style>