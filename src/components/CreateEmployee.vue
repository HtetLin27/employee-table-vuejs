<template>
  <div class="employeeTable container">
    <h2 class="employee-tabel-header">Create Employee</h2>
    <form class="employee-create-box">
      <div class="row">
        <div class="col-md-6">
          <input
            type="text"
            placeholder="Name"
            class="form-control"
            v-model="name"
          />
        </div>
        <div class="col-md-6">
          <input
            type="text"
            placeholder="Image URL"
            class="col-md-6"
            v-model="userImg"
          />
        </div>
      </div>
      <div class="row">
        <div class="col-md-6">
          <input type="text" placeholder="Email" v-model="email" />
        </div>
        <div class="col-md-6">
          <input type="text" placeholder="Phone" v-model="phone" />
        </div>
      </div>
      <div class="row">
        <div class="col-md-6">
          <select @change="getOffice($event)">
            <option>Select Office</option>
            <option value="Yangon Office">Yangon Office</option>
            <option value="Mandalay Office">Mandalay Office</option>
            <option value="Yangon Office Sue Lay">Yangon Office Sue Lay</option>
          </select>
        </div>
        <div class="col-md-6">
          <select @change="getDep($event)">
            <option>Select Department</option>
            <option value="Product Department">Product Department</option>
            <option value="Development">Development</option>
            <option value="Tech & Development">Tech & Development</option>
            <option value="Customer Success">Customer Success</option>
            <option value="Human Resource Managing Department">
              Human Resource Managing Department
            </option>
            <option value="Marketing Management">Marketing Management</option>
          </select>
        </div>
      </div>
      <div class="row">
        <div class="col-md-6">
          <input type="text" placeholder="Employee Code" v-model="empCode" />
        </div>
        <div class="col-md-6">
          <select @change="getPosition($event)" class="col-md-6">
            <option>Select Position</option>
            <option value="Developer">Developer</option>
            <option value="Intern">Inter</option>
            <option value="Trainee">Trainee</option>
            <option value="Manager">Manager</option>
            <option value="Marketing">Marketing</option>
          </select>
        </div>
      </div>

      <div class="row btn-group">
        <div class="col-md-12">
            <button @click=setEmployee class="create-btn"><span>Create</span> <i class="fa-solid fa-user-plus"></i></button>
        
            <button class="cancel-btn "><span>Cancel</span> <i class="fa-solid fa-xmark"></i></button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "EmployeeTable",
  components: {},
  data() {
    return {
      name: "",
      userImg: "",
      email: "",
      phone: "",
      office: "",
      department: "",
      empCode: "",
      position: "",
    };
  },
  methods: {
    getOffice(e) {
      this.office = e.target.value;
      console.log(this.office);
    },
    getDep(e) {
      this.department = e.target.value;
      console.log(this.department);
    },
    getPosition(e) {
      this.position = e.target.value;
      console.log(this.position);
    },
    async setEmployee() {
      if (this.name && this.email && this.phone && this.empCode) {
        const result = await axios.post("http://localhost:3000/employeelist", {
          name: this.name,
          userImg: this.userImg,
          email: this.email,
          phone: this.phone,
          office: this.office,
          department: this.department,
          empCode: this.empCode,
          position: this.position,
        });
        alert("Success Employee Creating");
        console.log(result);
      } else {
        alert("Please fill form!");
      }
    },
    cancelForm() {
      alert("Are you sure want to close?");
    },
  },
};
</script>

<style>
.employeeTable {
  width: 700px;
  position: absolute;
  top: 20%;
  left: 30%;
  background-color: #b5e2d0;
  border-radius: 20px;
}
.employee-tabel-header {
  text-align: center;
  padding-top: 25px;
  color: #2f3640;
}
.employee-create-box {
  padding: 10px 60px 30px 60px;
}
.employee-create-box input,
.employee-create-box select {
  /* margin: 5px; */
  margin-bottom: 20px;
  width: 255px;
  height: 45px;
  border: #fff;
  font-size: 16px;
  padding: 10px;
}
/* .employee-create-box select{
    margin: 5px;
} */
.btn-group {
  padding-top: 15px;
}
.create-btn {
  margin-left: 235px ;
  margin-right: 15px;
  padding: 10px;
  width: 150px;
  border-radius: 10px;
  font-size: 18px;
  cursor: pointer;
  background-color: #23d990;
  border: #23d990;
  color: #fff;
}
.create-btn span,
.cancel-btn span {
  margin-right: 10px;
}
.cancel-btn {
  padding: 10px;
  width: 150px;
  border-radius: 10px;
  font-size: 18px;
  cursor: pointer;
  background-color: #2f3640;
  border: #2f3640;
  color: #fff;
}
.create-btn:hover,
.cancel-btn:hover {
  color: #000;
}
select {
  appearance: none;
}
</style>
