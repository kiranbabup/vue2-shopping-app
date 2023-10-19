<template>
  <div id="app">
    <div class="header">
      <HeaderComponent :isLoginVisible="isLoginVisible" @login-open="loginOpen" :isRegisterVisible="isRegisterVisible"
       @register-open="registerOpen" />
    </div>
    <div class="body">
      <Login v-if="isLoginVisible"/>
      <Register v-if="isRegisterVisible"/>
    </div>
  </div>
</template>

<script>
import HeaderComponent from './components/header/HeaderComponent.vue';
import Login from './components/authentications/Login.vue';
import Register from './components/authentications/Register.vue';

export default {
  name: 'App',
  components: {
    HeaderComponent,
    Login,
    Register
  },
  data(){
    return{
      isLoginVisible: false,
      isRegisterVisible: false,
    }
  },
  methods:{
    loginOpen(l){
      this.isLoginVisible=l;
      this.isRegisterVisible=false;
    },
    registerOpen(r){
      this.isRegisterVisible=r;
      this.isLoginVisible=false;
    }
  }
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 100vw;
  height: 100vh;
}
.header{
  width: 100%;
  height: 3rem;
  background: linear-gradient(-90deg, rgb(239, 80, 80), rgb(117, 117, 239));
}
.body{
  width: 100%;
  height: calc(100% - 48px);
}
</style>
