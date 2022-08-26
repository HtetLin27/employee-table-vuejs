<template>
  <div class="employee-box">
  <Sidebar/>
  <Topbar/>
  </div>
  
</template>

<script>
import Sidebar from './components/Sidebar.vue';
import Topbar from './components/Topbar.vue';

export default {
  name: "App",
  components: {
    Sidebar,
    Topbar
},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.employee-box{
  display: flex;
}
</style>
