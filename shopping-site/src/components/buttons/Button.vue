<template>
    <div><button>{{ text }}</button></div>
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
    font-weight: bold;
    background-color:white;
    border-radius:25px;
    padding:0px 10px;
    height: 25px;
    width: auto;
    color: rgb(117, 117, 239);
    cursor: pointer;
}
button:hover{
    /* text-decoration: underline; */
    color: rgb(9, 69, 119);
}
</style>