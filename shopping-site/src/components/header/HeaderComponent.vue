<template>
    <div class="headerComponent">
        <span class="logo">ShoppingSite</span>
        <span class="loginSignupButtons">
            <div @click="onLoginBtnClick"><Button text="Login" ></Button></div> /
            <div @click="onRegisterBtnClick"><Button text="Register"></Button></div>
        </span>
    </div>
</template>
<script>
import Button from '../buttons/Button.vue';
export default {
    name: 'HeaderComponent',
    props:{
        isLoginVisible:{
            type:Boolean,
            required: true
        },
        isRegisterVisible:{
            type:Boolean,
            required: true
        }
    },
    data() {
        return {
        }
    },
    components: {
        Button
    },
    methods: {
        onLoginBtnClick() {
            this.isLoginVisible ? '' : this.$emit("login-open", true)
        },
        onRegisterBtnClick() {
            this.isRegisterVisible ? '' : this.$emit("register-open", true)
        },
    }
}
</script>
<style scoped>
.headerComponent {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo {
    margin-left: 2rem;
}

.loginSignupButtons {
    display: flex;
    gap: .3rem;
    margin-right: 2rem;
}
</style>