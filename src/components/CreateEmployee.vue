<template>
  <div class="employeeTable">
    <h2 class="employee-tabel-header">Create Employee</h2>
    <form class="employee-create-box">
        <input type="text" placeholder="Name"  v-model='name'/>
        <input type="text" placeholder="Image URL" v-model='userImg'/>
        <input type="text" placeholder="Emial"  v-model='email'/>
        <input type="text" placeholder="Phone"  v-model='phone'/>
        <select @change="getOffice($event)">
            <option>Office</option>
            <option value="Yangon Office">Yangon Office</option>
            <option value="Mandalay Office">Mandalay Office</option>
            <option value="Yangon Office Sue Lay">Yangon Office Sue Lay</option>
        </select>
        <select @change="getDep($event)">
            <option>Department</option>
            <option value="Product Department">Product Department</option>
            <option value="Development">Development</option>
            <option value="Tech & Development">Tech & Development</option>
            <option value="Customer Success">Customer Success</option>
            <option value="Human Resource Managing Department">Human Resource Managing Department</option>
            <option value="Marketing Management">Marketing Management</option>
        </select>
        <input type="text" placeholder="Employee Code"  v-model='empCode'/>
        <select @change="getPosition($event)">
            <option>Position</option>
            <option value="Developer">Developer</option>
            <option value="Intern">Inter</option>
            <option value="Trainee">Trainee</option>
            <option value="Manager">Manager</option>
            <option value="Marketing">Marketing</option>
        </select>
        <div class="button-group">
        <button @click=setEmployee class="create-btn">Create <i class="fa-solid fa-user-plus"></i></button>
        <button class="cancel-btn">Cancel <i class="fa-solid fa-xmark"></i></button>
        </div>
    </form>
  </div>
  
</template>

<script>

import axios from 'axios'
export default {
  name: "EmployeeTable",
  components: {
},
data(){
    return{
        name:"",
        userImg:"",
        email:"",
        phone:"",
        office:"",
        department:"",
        empCode:"",
        position:""
    }
},
methods:{
    getOffice(e){
        this.office =e.target.value;
        console.log(this.office)
    },
    getDep(e){
        this.department =e.target.value;
        console.log(this.department)
    },
    getPosition(e){
        this.position =e.target.value;
        console.log(this.position)
    },
    async setEmployee(){
        if(this.name && this.email && this.phone && this.empCode){     
            const result = await axios.post('http://localhost:3000/employeelist',{
                name:this.name,
                userImg:this.userImg,
                email:this.email,
                phone:this.phone,
                office:this.office,
                department:this.department,
                empCode:this.empCode,
                position:this.position
        }  )
        alert("Success Employee Creating")
        console.log(result);
        
        }else{
            alert("Please fill form!")
        }
        
    },
    cancelForm(){
        alert("Are you sure want to close?");
        
    }

}
};
</script>

<style>
.employeeTable{
    width: 600px;
    position: absolute;
    top: 20%;
    left: 30%;
    background-color:#23d990;
    border-radius: 20px;
    z-index: 9999;
}
.employee-tabel-header{
    text-align: center;
    padding-top: 10px;
    color: #fff;
}
.employee-create-box{
    padding: 10px 60px 30px 60px;

}
.employee-create-box input,.employee-create-box select{
    margin: 5px;
    width: 220px;
    height: 40px;
    border-radius: 10px;
    text-align: center;
    border: #fff;
    font-size: 16px;
}
.employee-create-box select{
    margin: 7px;

}
.button-group{
    text-align: center;
    padding-top: 10px;
}
.create-btn{
    padding: 10px;
    width: 180px;
    margin-right: 30px;
    border-radius: 10px;
    font-size: 18px;
    cursor: pointer;
    background-color: #eef202;
    border: #eef202;
}
.cancel-btn{
    padding: 10px;
    width: 180px;
    border-radius: 10px;
    font-size: 18px;
    cursor: pointer;
    background-color: #f20202;
    border: #f20202;
}
.create-btn:hover,.cancel-btn:hover{
  color: #fff;
}
select {
    appearance: none;
}

</style>