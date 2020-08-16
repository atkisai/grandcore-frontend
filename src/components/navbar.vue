<script>
  import axios from 'axios'

export default {
    components:{},
  data(){
    return{

    }
  },
  mounted(){

  },
  methods:{

  },
  computed:{

  }
}
</script>

<template>
  <div>
    <div>
        <nav class="navbar navbar-expand-lg navbar-light bg-light">
          <div class="collapse navbar-collapse" id="navbarNav">
    <ul class="navbar-nav">
      <li class="nav-item">
        <a class="nav-link" href="#" @click="$emit('home')">О фонде</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#" @click="$emit('getmoney')">Пожертвования</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#" @click="$emit('users')">Участники</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#" @click="$emit('news')">Новости</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#" @click="$emit('login')">Вход</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#" @click="$emit('reg')">Регистрация</a>
      </li>
    </ul>
  </div>
        </nav>
    </div>
  </div>
</template>

<style scoped>

</style>
