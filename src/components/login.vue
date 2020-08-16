<template>
  <div>
    <form method="post">
          <div class="form-group"><label for="id_email"></label><input type="email" name="email" autofocus class="form-control" placeholder="Адрес электронной почты" title="" required id="id_email" v-model="email"></div>
<div class="form-group"><label for="id_password1"></label><input type="password" name="password1" autocomplete="new-password" class="form-control" placeholder="Пароль" title="" required id="id_password1" v-model="pass"></div>
          <div class="form-group">
      <div class="row">
        <div class="col-xs-4 position-absolute" style="right: 50px;">
          <button type="submit" class="btn btn-primary btn-block btn-flat p-absolute right-0">Sign In</button>
        </div>
      </div>
        </div>
    </form>
  </div>
</template>

<script>
  import axios from 'axios'

  export default {
  data(){
    return{
      email:'',
      pass:'',
    }
  },
  methods:{
    post(){
      axios.post(localStorage.getItem("s")+'/login/', {email:this.email, password:this.pass})
        .then((response) => {
        if (response.data!='error') {
          localStorage.setItem("me", response.data.me);
          localStorage.setItem("token", response.data.token);
          localStorage.setItem("mypos", 'true');
          document.location.reload(true);
        }
        else{
          alert('Неверные данные!')
        }
});
    },
  }
}
</script>

<style>
  h1, h2 {
	text-align: center;
}
.button{
	margin-top: 10px;
}
  .field{
    text-align: center;
  }
   label {
   display: block;
  float: left;
  width: 70px;
  height: 15px;
  }
  .main{
    text-align: center;
    width: 230px;
    height: 329px;
  }
</style>

