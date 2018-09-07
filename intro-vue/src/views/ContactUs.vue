<template>
  <div id='contact' class='contact-body'>
    <router-view></router-view>
    <Header />
    <main class='contact-main'>
      <section class='contact-section'>
        <h1 class='contact-h1'>Contact Information</h1>
        <p class='contact-main-p'>For technical difficulties please contact Tom, R.J., Ryan or Natalie</p>
        <div class='contact-users'>
          <div class='contact-user'>
            <p class='contact-p-user'>Tom</p>
            <p class='contact-p-user'>thomas.clukies@gmail.com</p>
          </div>
          <div class='contact-user'>
            <p class='contact-p-user'>R.J.</p>
            <p class='contact-p-user'>rjkirkhope@gmail.com</p>
          </div>
          <div class='contact-user'>
            <p class='contact-p-user'>Ryan</p>
            <p class='contact-p-user'>ryanmccrory83@gmail.com</p>
          </div>
          <div class='contact-user'>
            <p class='contact-p-user'>Natalie</p>
            <p class='contact-p-user'>natalie.todd15@gmail.com</p>
          </div>
        </div>
      </section>
    </main>
    <Footer class='contact-footer' />
  </div>
</template>

<script scoped>
  import Header from "@/components/Header";
  import Footer from "@/components/Footer";
  export default {
    name: "Contact-Us",
    components: {
      Header,
      Footer
    }
  };
</script>

