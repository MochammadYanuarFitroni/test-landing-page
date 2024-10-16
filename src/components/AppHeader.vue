<template>
  <section class="header bg-yellow text-center py-5" ref="headerContent">
    <div class="container">
      <!-- <div class="logo">
        <img src="../path-to-your-logo.png" alt="Logo" class="logo-image" />
      </div> -->
      <div class="animated-content" ref="animatedContent">
        <h1 class="header-title">Innovative Solutions for Animals</h1>
        <p class="header-subtitle">charity organization</p>
        <div class="social-icons">
          <a href="#" class="social-icon">YouTube</a>
          <a href="#" class="social-icon">Instagram</a>
          <a href="#" class="social-icon">Facebook</a>
          <a href="#" class="social-icon">Patreon</a>
          <a href="#" class="social-icon">Telegram</a>
        </div>
        <!-- <a href="#" class="donate-button">donate</a> -->
      </div>
    </div>
  </section>
</template>

<script>
import ScrollMagic from "scrollmagic";

export default {
  mounted() {
    const controller = new ScrollMagic.Controller();
    new ScrollMagic.Scene({
      triggerElement: this.$refs.animatedContent, 
      triggerHook: 0.8,
      duration: '100%',
      reverse: true,
    })
      .setClassToggle(this.$refs.animatedContent, "fade-in") 
      .addTo(controller);
  },
};
</script>

<style scoped>
.header {
  width: 100vw;
  height: 100vh;
  background-color: #f6e02d; 
  color: #000; 
  display: flex; 
  align-items: center;
  justify-content: center; 
}

.animated-content {
  opacity: 0; 
  transform: translateY(30px); 
}

.fade-in {
  opacity: 1;
  transform: translateY(0); 
  transition: opacity 0.6s ease-out, transform 0.6s ease-out; 
}

.header-title {
  font-size: 3rem;
}

.header-subtitle {
  font-size: 1.5rem; 
  margin: 10px 0;
}

.social-icons {
  margin: 20px 0;
}

.social-icon {
  margin: 0 10px;
  text-decoration: none; 
  color: inherit;
}

.donate-button {
  display: inline-block;
  padding: 10px 20px;
  background-color: #000; 
  color: #fff; 
  border-radius: 5px; 
  text-decoration: none; 
  font-weight: bold;
}
</style>
