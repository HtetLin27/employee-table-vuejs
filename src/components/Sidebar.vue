<template>
<div class="sidebar">
<img class="logo" width="60" height="60" src="../assets/BHlogo.png"/>

<nav class="sidebar-nav">
  <li><i class="fa-solid fa-desktop"></i></li>
  <li><i class="fa-regular fa-clock"></i></li>
  <li><i class="fa-solid fa-briefcase"></i></li>
  <li><i class="far fa-calendar-plus"></i></li>
  <li><i class="fas fa-user"></i></li>
  <li><i class="fas fa-sync"></i></li>
  <li><i class="fa-regular fa-bell"></i></li>
  <li><i class="fa-regular fa-credit-card"></i></li>
  <li><i class="far fa-comment-alt"></i></li>
  <li><span class="more-icon"><i class="fas fa-ellipsis-h"></i></span>
     <p class="more">More</p> 
  </li>
  <div class="user-box">
   <li><i class="fa-solid fa-download"></i></li>
   <li><i class="fa-regular fa-message"></i></li>
   <li>
    <img class="user-img" src="https://randomuser.me/api/portraits/men/42.jpg"/>
   </li>
  </div>

</nav>
</div>

</template>

<script>
export default {
  name: "Sidebar",
  
};

</script>

<style>
.sidebar{
  flex: 1.2;
  background-color:  #f5f6fa;

}
.sidebar-nav{
  display: flex;
  flex-direction: column;
  align-items: center;
  
  }
.logo{
  padding-top: 5px;
  padding-left: 3px;
  margin-bottom: 15px;
}
.sidebar-nav li{
  list-style: none;
  font-size: 22px;
  margin-bottom: 10px;
  cursor: pointer;
}

.sidebar-nav li:hover{
  color: #4cd137;

}
.more-icon{
  margin-left: 5px;
}
.more{
  position: relative;
  top:-15px;
  left: -3px;
  font-size: 16px;
}
.user-img{
  width: 40px;
  height: 40px;
  border-radius:50%;
}
.user-box{
  margin-top: 40px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

</style>