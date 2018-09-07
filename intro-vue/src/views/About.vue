<template>
    <div id='about' class='about'>
        <router-view></router-view>
        <Header />
        <h1 class='about-h1'>About your friendly Travel Bug Developers</h1>
        <main class='about-main'>
            <section class='about-us'>
                <div class='about-div'>
                    <h2 class='about-h2'>Thomas Clukies</h2>
                    <img src='https://media.licdn.com/dms/image/C4E03AQGESCp6uZoaFQ/profile-displayphoto-shrink_800_800/0?e=1539820800&v=beta&t=zyZGBq9E3aH8H5SkhaAEmlURPlongDD3Jqk8SGLjAV8' class='about-img'>
                    <p class="about-p">Phone: (303)406-3835 </p>
                    <p class="about-p">Email: thomas.clukies@gmail.com</p>
                    <a class="about-link" href='https://github.com/tclukies'>GitHub</a>
                    <a class="about-link" href='https://www.linkedin.com/in/thomas-clukies/'>LinkedIn</a>
                </div>
                <div class='about-div'>
                    <h2 class='about-h2'>R.J. Kirkhope</h2>
                    <img src='https://media.licdn.com/dms/image/C4E03AQG4ZM2q1Ite_Q/profile-displayphoto-shrink_800_800/0?e=1539820800&v=beta&t=jmVpGWBXklqJFnu7Eg7QGPwi12GpFUzbxk79KJWkYG8' class='about-img'>
                    <p class="about-p">Phone: (303) 717-3002 </p>
                    <p class="about-p">Email: rjkirkhope@gmail.com</p>
                    <a class="about-link" href='https://github.com/rjkirkhope'>GitHub</a>
                    <a class="about-link" href='https://www.linkedin.com/in/robert-kirkhope/'>LinkedIn</a>
                </div>
                <div class='about-div'>
                    <h2 class='about-h2'>Ryan McCrory</h2>
                    <img src='https://media.licdn.com/dms/image/C5603AQEydsW4sLA8bg/profile-displayphoto-shrink_800_800/0?e=1539820800&v=beta&t=Bej1VdnGOCKVUYp8zuv5NL4Kzaxp740nPz9LbnZV0qI' class='about-img'>
                    <p class="about-p">Phone: (303) 709-9989</p>
                    <p class="about-p">Email: ryanmccrory83@gmail.com</p>
                    <a class="about-link" href='https://github.com/ryanmccrory83/'>GitHub</a>
                    <a class="about-link" href='https://www.linkedin.com/in/ryan-mccrory83/'>LinkedIn</a>
                </div>
                <div class='about-div'>
                    <h2 class='about-h2'>Natalie Todd</h2>
                    <img src='https://media.licdn.com/dms/image/C5603AQF4UW_luFwmXQ/profile-displayphoto-shrink_800_800/0?e=1539820800&v=beta&t=8HZh5_TybesLzGGGKYdTAN7SFETpW5pDpM6CpCVrf7g' class='about-img'>
                    <p class="about-p">Phone: (907) 317-7907 </p>
                    <p class="about-p">Email: natalie.todd15@gmail.com</p>
                    <a class="about-link" href='https://github.com/natalie-todd'>GitHub</a>
                    <a class="about-link" href='https://www.linkedin.com/in/natalie-todd/'>LinkedIn</a>
                </div>
            </section>
        </main>
        <Footer />
    
    
    </div>
</template>

<script>
    import Header from "@/components/Header";
    import Footer from "@/components/Footer";
    export default {
        name: "About",
        components: {
            Header,
            Footer
        }
    };
</script>

<style>
    .about-us {
        display: flex;
        justify-content: space-around;
    }
    
    .about-div {
        display: flex;
        flex-flow: column;
        justify-content: center;
        align-items: center;
        background-color: #9fb1bcc2;
        border-radius: 15px;
        box-shadow: 8px 8px 8px #444545;
        width: 20vw;
    }
    
    .about-img {
        width: 15vw;
    }
    
    .about-h1 {
        padding-top: 5vh;
        padding-bottom: 5vh;
        text-align: center;
        font-size: 2em;
        color: #086788;
        text-shadow: -1px -1px 1px white, 1px 1px 1px white, -1px 1px 1px white, 1px -1px 1px white;
        font-family: "Slackey";
    }
    
    .about-h2 {
        font-size: 1.5em;
        color: #086788;
        text-shadow: -1px -1px 1px white, 1px 1px 1px white, -1px 1px 1px white, 1px -1px 1px white;
        font-family: "Slackey";
    }
    
    .about-p {
        margin-bottom: 0;
        color: #086788;
        font-family: "Simonetta";
    }
    
    .about-link {
        text-decoration: none;
        color: #086788;
        font-family: "Simonetta";
    }
</style>