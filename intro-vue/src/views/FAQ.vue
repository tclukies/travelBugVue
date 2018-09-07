<template>
  <div id='faq'>
    <router-view></router-view>
    <Header />
    <h1 class="faq-header">Frequently Asked Questions</h1>
    <div class="faq-q">
      <p class='faq-question'>Who is this app for?</p>
      <p class='faq-answer'>Any human with the passion for travel! Quickly and easily search for locations you want to visit with our interactive app, then add countries you wish to visit to your bucket list. Input activities or cities you want to visit, and when you want to
        visit them.</p>
    </div>
    <div class="faq-q">
      <p class='faq-question'>What problem does this app solve?</p>
      <p class='faq-answer'>Travel Bug gives you a platform to congregate all of your bucket list travel destinations and activities! It's a fun, interactive way to keep track of countries you have visited and countries you would like to visit. It can also keep you on track
        and help you plan times and places to visit.</p>
    </div>
    <div class="faq-q">
      <p class='faq-question'>What is next for Travel Bug? </p>
      <p class='faq-answer'>Travel! And many more app improvements. We would like to move to a social platform where locations can be shared with your friends. We would like for users to be able to find people longing to visit the same locations and be able to connect those
        users through our platform. We would also like the map to show the locations with markers, and possibly already visited locations so users can see their progress!</p>
    </div>
    <div class="faq-q">
      <p class='faq-question'>How do I change users?</p>
      <p class='faq-answer'>Click on the sign out button at the top of the page to take you to the login page.</p>
    </div>
    <div class="faq-q">
      <p class='faq-question'>How do I input a new location with activities on my map?</p>
      <p class='faq-answer'>Click on the input area named location and type in the country destination. After that, click on the text area named activities and input the desired activities to be accomplished.</p>
    </div>
    <div class="faq-q">
      <p class='faq-question'>How do I delete a post?</p>
      <p class='faq-answer'>On each post card, there is a small "x" in the upper right hand corner! Just hit then and confirm the deletion.</p>
    </div>
    <Footer />
  </div>
</template>

<script scoped>
  import Header from "@/components/Header";
  import Footer from "@/components/Footer";
  export default {
    name: "FAQ",
    components: {
      Header,
      Footer
    }
  };
</script>

<style>
  .faq-header {
    padding-top: 5vh;
    padding-bottom: 5vh;
    text-align: center;
    font-size: 2em;
    color: #086788;
    text-shadow: -1px -1px 1px white, 1px 1px 1px white, -1px 1px 1px white, 1px -1px 1px white;
    font-family: "Slackey";
  }
  
  .faq-q {
    display: flex;
    flex-flow: column;
    justify-content: center;
    justify-content: space-between;
    align-items: center;
    background-color: #9fb1bcd3;
    border-radius: 15px;
    box-shadow: 8px 8px 8px #444545;
    margin-bottom: 3vh;
    margin-left: 10vw;
    margin-right: 10vw;
    padding-left: 1vw;
    color: #086788;
    font-family: "Simonetta";
  }
</style>