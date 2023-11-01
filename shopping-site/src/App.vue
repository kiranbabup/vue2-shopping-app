<template>
  <div id="app">
    <div class="header">
      <HC
        :isLoginVisible="isLoginVisible"
        @login-open="loginOpen"
        :isRegisterVisible="isRegisterVisible"
        @register-open="registerOpen"
      />
    </div>
    <div class="body">
      <Login v-if="isLoginVisible" @on-close="onClose" />
      <Register v-if="isRegisterVisible" @on-close="onClose" />

      <div v-for="product in productsData" :key="product.id" class="cardArea">
        <div class="card">
          <p>{{ product.title.slice(0,25) }}</p>
          <img :src="product.image" :alt="product.description" width="100" height="100" />
        </div>
      </div>

    </div>
  </div>
</template>

<script>
import HC from "./components/header/HeaderComponent.vue";
import Login from "./components/authentications/Login.vue";
import Register from "./components/authentications/Register.vue";
import "whatwg-fetch";

export default {
  name: "App",
  components: {
    HC,
    Login,
    Register,
  },
  data() {
    return {
      isLoginVisible: false,
      isRegisterVisible: false,
      productsData: [],
    };
  },
  methods: {
    loginOpen(l) {
      this.isLoginVisible = l;
      this.isRegisterVisible = false;
    },
    registerOpen(r) {
      this.isRegisterVisible = r;
      this.isLoginVisible = false;
    },
    onClose(c) {
      this.isLoginVisible
        ? (this.isLoginVisible = c)
        : this.isRegisterVisible
        ? (this.isRegisterVisible = c)
        : "";
    },
    fetchData() {
      fetch("https://fakestoreapi.com/products")
        .then((res) => res.json())
        .then((data) => {
          console.log(data, "data");
          this.productsData = data;
        })
        .catch((error) => {
          console.error("Error fetching", error);
        });
    },
  },
  created() {
    console.log("created");
    this.fetchData();
  },
};
</script>

<style>
* {
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
.header {
  width: 100%;
  height: 3rem;
  background: linear-gradient(-90deg, rgb(239, 80, 80), rgb(117, 117, 239));
}
.body {
  width: 100%;
  height: calc(100% - 48px);
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;
}
.card{
  /* background-color: aqua; */
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 20rem;
  height: 10rem;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  border-radius: 25px;
}
</style>
