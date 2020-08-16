<template>
  <div id="app">
    <navbar @reg="reg" @login="login" @home="home" @getmoney="getmoney" @users="users" @news="news"></navbar>
    <home v-if="state=='home'"></home>
    <reg v-else-if="state=='reg'"></reg>
    <login v-else-if="state=='login'"></login>
    <getmoney v-else-if="state=='getmoney'"></getmoney>
    <news v-else-if="state=='news'"></news>
    <users v-else-if="state=='users'"></users>
  </div>
</template>

<script>
import axios from 'axios'
import navbar from './components/navbar.vue'
import reg from './components/reg.vue'
import login from './components/login.vue'
import home from './components/home.vue'
import getmoney from './components/getmoney.vue'
import users from './components/users.vue'
import news from './components/news.vue'
export default {
  name: 'app',
  components:{navbar, home, reg, login, getmoney, users, news},
  data(){
    return{
      server:'http://127.0.0.1/api',
      state:'home',
      user:'',
    }
  },
  mounted(){
    this.myServer()
  },
  methods:{
    myServer(){
      localStorage.setItem("s", this.server)
    },
    reg(){
      this.state='reg'
    },
    login(){
      this.state='login'
    },
    home(){
      this.state='home'
    },
    getmoney(){
      this.state='getmoney'
    },
    users(){
      this.state='users'
    },
    news(){
      this.state='news'
    },
  },
 }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
