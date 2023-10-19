<template>
        <button>{{ text }}</button>
</template>
<script>
export default{
    name:'Button',
    props:['text'],
}
</script>
<style>
button{
    border: none;
    background: none;
    /* color: white; */
    font-weight: bold;
    background-color:white;
    border-radius:50px;
    padding:0px 10px;
}
button:hover{
    text-decoration: underline;
    color: rgb(9, 69, 119);
}
</style>