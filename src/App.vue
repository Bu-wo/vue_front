<template>
  <ul>
    <li v-for="(item) in users" :key="item.id">{{item.name}}</li>
  </ul>
</template>

<script>
import axios from "axios"
export default {
  name: 'App',
  data(){
    return{
      users:[]
    }
  },
  mounted(){
    axios.get('http://localhost:3000/api/users').then(res=>{
      console.log(res.data)
      this.users = res.data;
    })
  }
}
</script>

<style>
</style>
