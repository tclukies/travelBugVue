<template>
    <div class='content'>
        <div class="title">
            <h1>Welcome to Travel Bug!</h1>
            <div class="bug-div">
                <img id="travel-bug" src="../assets/TravelBug.png" class="dion">
            </div>
        </div>
        <div>
            <div class='modal-container'>
                <div class='modal-header'>
                    <slot name='login'>
                        <div v-if='logseen' id='signin'>
                            <form>
                                <h3 class="modal-h3">Come Explore!</h3>
                                <div class="login">
                                    <input placeholder='Username' type='text' name='username' id='username' value=''>
                                    <input placeholder='Password' type='password' name='password' id='password' value=''>
                                    <input @click.prevent='bool' type='submit' value='Sign In' class='signButton'>
                                </div>
                                <div class="new-to">
                                    <label for='login'>New to Travel Bug?</label>
                                </div>
                                <div>
                                    <button v-on:click.prevent='registerSeen = true,  logseen = false' type='submit' class="signButton" name='button'>Sign up now!</button>
                                </div>
                                <div id="alertMessage">
                                    <p></p>
                                </div>
                            </form>
                        </div>
                    </slot>
                    <slot name='register'>
                        <div v-if='registerSeen' id='registrationForm'>
                            <form v-on:submit.prevent='checkFields()'>
                                <h3>We are excited for your new ventures!</h3>
                                <p class="error-message"></p>
                                <p class="success-message"></p>
                                <div>
                                    <input placeholder='First Name' type='text' v-model="firstName" name='firstName' id='firstName' value=''>
                                </div>
                                <div>
                                    <input placeholder='Last Name' type='text' v-model="lastName" name='lastName' id='lastName' value=''>
                                </div>
                                <div>
                                    <input placeholder='Email' type='text' v-model="email" name='email' id='email' value=''>
                                </div>
                                <div>
                                    <input placeholder='Username' type='text' v-model="registerUsername" name='registerUsername' id='username' value=''>
                                </div>
                                <div>
                                    <input placeholder='Password' type='text' v-model="registerPassword" name='registerPassword' id='passWord' value=''>
                                </div>
                                <div>
                                    <button type='submit' class="signButton" name='button'>Create Profile</button>
                                </div>
                            </form>
                        </div>
                    </slot>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Modal",
        data() {
            return {
                registerSeen: false,
                logseen: true,
                name: "modal",
                signinUrl: "https://travel-bug-backend.herokuapp.com/profiles",
                form: {
                    username: "",
                    password: ""
                },
                profileData: null,
                firstName: "",
                lastName: "",
                email: "",
                registerUsername: "",
                registerPassword: "",
                registerUrl: "https://travel-bug-backend.herokuapp.com/profiles"
            };
        },
        mounted() {
            fetch(this.signinUrl, {
                    method: "get",
                    mode: "cors",
                    credentials: "same-origin",
                    headers: new Headers({
                        "Content-Type": "application/json"
                    })
                })
                .then(resp => resp.json())
                .then(resp => {
                    this.profileData = resp;
                })
        },
    
        methods: {
            verified(userid) {
                this.$router.push({
                    path: "main",
                    query: {
                        user: userid
                    }
                });
            },
            notVerified() {
                document.querySelector("#alertMessage").textContent =
                    "Incorrect username or password. Please try again!";
            },
            bool() {
                for (let i = 0; i < this.profileData.profile.length; i++) {
                    if (
                        document.querySelector("#username").value ===
                        this.profileData.profile[i].username &&
                        document.querySelector("#password").value ===
                        this.profileData.profile[i].password
                    ) {
                        this.verified(this.profileData.profile[i].id);
                    } else {
                        this.notVerified();
                    }
                }
            },
            checkFields() {
                let newPost = {
                    first_name: this.firstName,
                    last_name: this.lastName,
                    email: this.email,
                    username: this.registerUsername,
                    password: this.registerPassword
                };
                if (
                    this.firstName !== "" &&
                    this.lastName !== "" &&
                    this.email !== "" &&
                    this.registerUsername !== "" &&
                    this.registerPassword !== ""
                ) {
                    fetch(this.registerUrl, {
                            method: "POST",
                            headers: {
                                Accept: "application/json",
                                "Content-Type": "application/json"
                            },
                            body: JSON.stringify(newPost)
                        })
                        .then(res => res.json())
                        .then(document.querySelector(".success-message").textContent = "Profile Created!")
                        .then(
                            setTimeout(function() {
                                location.reload();
                            }, 1000)
                        );
                } else {
                    document.querySelector(".error-message").textContent =
                        "Please fill out all feilds!";
                }
            }
        }
    };
</script>

<style scoped>
    .content {
        display: flex;
        flex-flow: column;
        justify-content: center;
        align-items: center;
        color: #086788;
        text-shadow: -2px -2px 2px white, 2px 2px 2px white, -2px 2px 2px white, 2px -2px 2px white;
        font-family: "Slackey";
    }
    
    .title {
        display: flex;
        flex-flow: column;
        justify-content: center;
        align-items: center;
        margin-top: 6vh;
        margin-bottom: 3vh;
    }
    
    .new-to {
        text-shadow: none;
        text-shadow: -2px -2px 2px white, 2px 2px 2px white, -2px 2px 2px white, 2px -2px 2px white;
        font-family: "Slackey";
    }
    
    #alertMessage {
        text-shadow: none;
    }
    
    @keyframes flip-bug {
        0% {
            transform: scaleX(-1);
            margin-left: 0px;
        }
        5% {
            transform: scaleX(1);
        }
        47% {
            transform: scaleX(1);
        }
        50% {
            margin-left: 350px;
        }
        53% {
            transform: scaleX(-1);
        }
        95% {
            transform: scaleX(-1);
        }
        100% {
            transform: scaleX(-1);
            margin-left: 0px;
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
    
    #travel-bug {
        animation: flip-bug 5s infinite;
        animation-timing-function: linear;
    }
    
    .bug-div {
        width: 500px;
        animation: bounce-bug-div 5s infinite;
    }
    
    .login {
        margin-top: 5vh;
        margin-bottom: 5vh;
        font-family: "Simonetta";
    }
    
    .modal-header {
        display: flex;
        justify-content: center;
        background-color: #9fb1bca8;
        border-radius: 15px;
        box-shadow: 8px 8px 8px #444545;
        border: 0px;
    }
    
    .modal-h3 {
        color: #086788;
        text-shadow: -2px -2px 2px white, 2px 2px 2px white, -2px 2px 2px white, 2px -2px 2px white;
        font-family: "Slackey";
    }
    
    #signin {
        display: flex;
        flex-wrap: column;
        justify-content: center;
        align-items: center;
        font-family: "Simonetta";
    }
    
    .signButton {
        background-color: #9fb1bc;
        color: #086788;
        box-shadow: 3px 3px 3px #444545;
        border: 0px;
        font-family: "Simonetta";
    }
    
    form {
        display: flex;
        flex-flow: column;
        justify-content: center;
        align-items: center;
    }
</style>