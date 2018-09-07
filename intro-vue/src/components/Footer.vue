<template>
    <div class='footer'>
        <router-link to='/about' class='anchor'>About</router-link>
        <router-link to='/faq' class='anchor'>FAQ</router-link>
    </div>
</template>

<script>
    export default {
        name: "Footer",
        data() {
            return {
                msg: "Welcome to Your Vue.js App"
            };
        }
    };
</script>

<style>
    .footer {
        text-decoration: none;
        margin-left: 40%;
        margin-right: 40%;
        position: center;
        bottom: 0;
        position: fixed;
        width: 20%;
        text-align: center;
        background-color: rgba(255, 255, 255, 0.418);
        border-radius: 15px;
        color: #086788;
        text-shadow: -2px -2px 2px white, 2px 2px 2px white, -2px 2px 2px white, 2px -2px 2px white;
        font-family: "Slackey";
        display: flex;
        justify-content: space-around;
    }
    
    .first {
        display: flex;
        height: 90vh;
    }
</style>