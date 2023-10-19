<template>
    <div class="loginPage">
        <div class="login">
            <span>
                <h2>login page</h2>
                <Button text="X" />
            </span>
            <form>
                <label>Username: <input /></label>
                <label>Password: <input /></label>
                <Button text="Login" />
            </form>
        </div>
    </div>
</template>
<script>
import Button from '../buttons/Button.vue';

export default {
    name: 'Login',
    components: {
        Button
    },
}
</script>
<style scoped>
.loginPage {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.login {
    width: 25%;
    height: auto;
    border: 1px solid black;
    border-radius: 25px;
    background-color: rgb(117, 117, 239);
    display:flex;
    flex-direction: column;
    align-items:center;
    gap:1rem;
    padding:1rem;
}
span{
    width:100%;
    display:flex;
    justify-content:space-around;
}
form{
    width:100%;
    display:flex;
    flex-direction: column;
    align-items:center;
    gap:1rem;
}
</style>