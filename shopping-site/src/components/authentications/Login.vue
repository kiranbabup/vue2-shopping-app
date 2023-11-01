<template>
  <div class="loginPage">
    <div class="login">
      <span>
        <h2>Login page</h2>
        <div @click="loginCloseBtnClick"><Button text="X" /></div>
      </span>
      <form @submit.prevent="()=>{}">
        <article>
          <label>Username</label
          ><input
            type="text"
            name="userName"
            autocomplete="off"
            v-model="userName"
          />
        </article>
        <article>
          <label>Password</label
          ><input
            type="password"
            name="password"
            autocomplete="off"
            v-model="password"
          />
        </article>
        <Button type="submit" text="Login" />
      </form>
    </div>
  </div>
</template>
<script>
import Button from "../buttons/Button.vue";

export default {
  name: "Login",
  components: {
    Button,
  },
  data() {
    return {
      userName: "",
      password: "",
    };
  },
  methods: {
    loginCloseBtnClick() {
      this.$emit("on-close", false);
    },
  },
};
</script>
<style scoped>
.loginPage {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
}

.login {
  width: 25%;
  height: auto;
  border: 1px solid black;
  border-radius: 25px;
  background-color: rgb(117, 117, 239);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
  padding: 1rem;
}
span {
  width: 100%;
  display: flex;
  justify-content: space-around;
}
form {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}
h2 {
  width: 80%;
  text-align: center;
  padding-left: 2rem;
}
article {
  width: 65%;
  display: flex;
  justify-content: space-between;
}
</style>
