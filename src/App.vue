<template>
  <h1>Contact List</h1>
  <br>
  <br>
 <div id="container" v-for="(user, index) in users" :key="index">
    <table class="Contacts">
      <thead>
        <tr class="header">
          <th> 💬 Name</th>
          <th> ✉️ Email</th>
          <th> 📍 Address</th>
        </tr>
      </thead>
      <tbody>
        <td>{{ user.name }}</td>
        <td>{{ user.email }}</td>
        <td>{{ user.address.street }}, {{user.address.suite}}, {{user.address.city}}</td>
      </tbody>
      <br>
    </table>
  </div>
 </template>
 

<script>
import axios from 'axios'


export default {
 data(){
   return {
     users: []
   }
 },
 mounted(){
   axios.get('https://jsonplaceholder.typicode.com/users')
   .then(response => this.users = response.data)
 }
}
</script>
<style>

table {
  table-layout: fixed;
  border-collapse:collapse;
  border-spacing: 0 15px;
  width: 100%;
  height:100%;
}

th {
  background-color:wheat;
  color: brown;
}

th,
td {
  width: 200px;
  text-align: center;
  padding: 5px;
}

h2 {
  color: white;
}
#app {
 font-family: Avenir, Helvetica, Arial, Arial;
 background:wheat;
 background-image: url(stars.jpg);
 background-blend-mode:soft-light;
 -webkit-font-smoothing: antialiased;
 -moz-osx-font-smoothing: grayscale;
 text-align: center;
 color: brown;
}
</style>

