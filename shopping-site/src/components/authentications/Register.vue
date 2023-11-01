<template>
    <div class="register-page">
        <div class="registerBox">
            <span>
                <h2>Register page</h2>
                <div @click="registerCloseBtnClick"><Button text="X" /></div>
            </span>
            <form>
                <article><label>First Name</label><input type="text" name="firstName" v-model="firstName" autocomplete="off"/></article>
                <article><label>Last Name</label><input type="text" name="lastName" v-model="lastName" autocomplete="off" /></article>
                <article><label>Email</label><input type="email" name="email" v-model="email" autocomplete="off" /></article>
                <article><label>Phone</label><input type="number" name="phone" v-model="phone" autocomplete="off" /></article>
                <article><label>Password</label><input type="password" name="password" v-model="password" autocomplete="off" /></article>                
                <Button text="Register" />
            </form>
        </div>
    </div>
</template>
<script>
import Button from '../buttons/Button.vue';

export default{
    name: "Register",
    components: { Button },
    data(){
        return{
            firstName: "",
            lastName: "",
            email: "",
            phone: "",
            password: ""
        }
    },
    methods:{
        registerCloseBtnClick(){
            this.$emit('on-close', false);
        }
    }
}
</script>
<style scoped>
.register-page {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    color: #fff;

}

.registerBox {
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
h2{
    width: 80%;
    text-align: center;
    padding-left: 2rem;
}
form{
    width:100%;
    display:flex;
    flex-direction: column;
    align-items:center;
    gap:1rem;
}
article{
    width: 65%;
    display: flex;
    justify-content: space-between;
}
</style>