<template>
  <div id="app">
   <ul>
     <li v-for="user in users" :key=user.id>
       {{user}}
     </li>
   </ul>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import axios from 'axios'
export default {
  name: 'App',
  data() {
    return {
      users: []
    }
  },
  mounted() {
    axios.get('http://localhost:3000/api/users').then(res => {
      this.users = res.data;
    })
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
