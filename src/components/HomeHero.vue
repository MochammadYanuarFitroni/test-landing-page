<template>
  <div class="section">
    <div class="background white"></div>
    <div class="padding-vertical">
      <div class="container" ref="containerContent">
        <h2 class="h2-section-work">We are</h2>
        <div class="big-text-work">a team of like-minded people, socially active companies, media personalities,
          volunteers who help low-income shelters and foster carers to support homeless animals.</div>
        
        <h2 class="h2-section-work">Our primary goal</h2>
        <div class="big-text-work">is to provide animals with the most necessary things - food, medicine, and urgent
          needs for the livelihood of shelters. We believe in our power and the power of conscious citizens who
          care about the environment and their health, who understand the importance of helping each other,
          especially our little friends. Growth begins with your care for your loved ones. Animals are one of the
          closest creatures to humans who remain with us throughout our lives. We all know the healing power of
          warmth, grace, and big loving eyes.</div>
        
        <blockquote class="big-text-work quote">"Animals need to have friends. Just like humans." <br>- James
          Herriot, All Creatures Great and Small<br></blockquote>
        
        <div class="big-text-work">Who else if not we should support our younger brothers, especially in difficult
          times? Let's be friends!</div>
        
        <div data-w-id="19a0cdfd-2e40-50c6-1ce2-1db9af2c96ca"
          style="opacity: 0; transform: translate3d(0px, 100px, 0px);"
          class="video-wrapper">
          <div style="padding-top:56.17021276595745%" class="w-video w-embed">
            <iframe class="embedly-embed"
              src="//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2F5Wk1rp99B7o%3Ffeature%3Doembed&amp;display_name=YouTube&amp;url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D5Wk1rp99B7o&amp;image=https%3A%2F%2Fi.ytimg.com%2Fvi%2F5Wk1rp99B7o%2Fhqdefault.jpg&amp;key=96f1f04c5f4143bcb0f2e68c87d65feb&amp;type=text%2Fhtml&amp;schema=youtube"
              scrolling="no" allowfullscreen=""
              title="Допоможи тваринам України/ Help the animals of Ukraine"></iframe>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ScrollMagic from "scrollmagic";

export default {
  mounted() {
    const controller = new ScrollMagic.Controller();

    new ScrollMagic.Scene({
      triggerElement: this.$refs.containerContent, 
      triggerHook: 0.8, 
      duration: '100%', 
      reverse: true, 
    })
      .setClassToggle(this.$refs.containerContent, "fade-in") 
      .addTo(controller);
  },
};
</script>

<style scoped>
.section {
  height: 100vh; 
  display: flex; 
  align-items: center; 
  justify-content: center; 
}

.fade-in {
  opacity: 1 !important; 
  transform: translateY(0) !important; 
  transition: opacity 0.6s ease-out, transform 0.6s ease-out; 
}

.container {
  opacity: 0;
  transform: translateY(30px); 
  transition: opacity 0.6s ease-out, transform 0.6s ease-out;
  display: flex; 
  flex-direction: column; 
  align-items: center; 
  justify-content: center; 
  height: 100%; 
}

.h2-section-work {
  margin: 20px 0; 
}

.big-text-work {
  margin: 10px 0; 
  text-align: center; 
}
</style>
