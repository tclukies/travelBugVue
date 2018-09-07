<template>
    <div class="header-1">
        <div class="bug-div">
            <img src="../assets/TravelBug.png" class="dion1">
        </div>
        <h1 class="travel-bug">Travel Bug</h1>
        <router-link to='/' tag='button' class="header-1-logout">Logout</router-link>
    </div>
</template>

<script>
    export default {
        name: "Header",
        data() {
            return {
                msg: "Welcome to Your Vue.js App"
            };
        }
    };
</script>

<style>
    .header-1 {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-top: 1vh;
        margin-left: 10vh;
        margin-right: 10vh;
    }
    
    .travel-bug {
        color: #086788;
        text-shadow: -2px -2px 2px white, 2px 2px 2px white, -2px 2px 2px white, 2px -2px 2px white;
        font-family: "Slackey";
        text-align: center;
    }
    
    .header-1-logout {
        background-color: white;
        color: #086788;
        height: 5vh;
        border-radius: 10px;
        box-shadow: 3px 3px 3px #444545;
    }
    
    @keyframes flip-bug {
        0% {
            transform: scaleX(-1);
            margin-left: -50px;
        }
        5% {
            transform: scaleX(1);
        }
        47% {
            transform: scaleX(1);
        }
        50% {
            margin-left: 250px;
        }
        53% {
            transform: scaleX(-1);
        }
        95% {
            transform: scaleX(-1);
        }
        100% {
            transform: scaleX(-1);
            margin-left: -50px;
        }
    }
    
    @keyframes bounce-bug-div {
        0% {
            transform: translateY(0);
        }
        10% {
            transform: translateY(15px);
        }
        20% {
            transform: translateY(0);
        }
        30% {
            transform: translateY(15px);
        }
        40% {
            transform: translateY(0);
        }
        50% {
            transform: translateY(15px);
        }
        60% {
            transform: translateY(0);
        }
        70% {
            transform: translateY(15px);
        }
        80% {
            transform: translateY(0);
        }
        90% {
            transform: translateY(15px);
        }
        100% {
            transform: translateY(0);
        }
    }
    
    .dion1 {
        height: 12vh;
        animation: flip-bug 5s infinite;
        animation-timing-function: linear;
    }
    
    .bug-div {
        width: 50px;
        animation: bounce-bug-div 5s infinite;
    }
</style>