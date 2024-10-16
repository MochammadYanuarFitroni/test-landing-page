<template>
  <div class="section">
    <div class="background blue"></div>
    <div class="padding-vertical">
      <div id="projects" class="container" ref="aboutContent">
        <h2 class="h2-section-work white">Our projects</h2>
        <div class="big-text-work white">are very different in terms of priority, scale and complexity of
          implementation</div>
        <div class="collection-list-wrap w-dyn-list">
          <div role="list" class="collection-list---projects w-dyn-items">
            <div v-for="(project, index) in projects" :key="index" 
              :style="{ backgroundColor: project.bgColor }"
              class="collection-item---projects w-dyn-item" 
              :ref="'projectItem' + index">
              <a :href="project.link" class="project-link-wrap w-inline-block">
                <div class="project-wrap">
                  <div class="project-title">{{ project.title }}</div>
                  <div class="small-text-work last-item">{{ project.description }}</div>
                </div>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ScrollMagic from "scrollmagic";

export default {
  data() {
    return {
      projects: [
        {
          title: "Emergency Aid. WAR 2022.",
          description: "Providing food and medicine to the shelters and animals which lost their homes and families due to the war",
          link: "/project/emergency-aid-war-2022",
          bgColor: "rgb(0, 0, 0)"
        },
        {
          title: "Non-commercial feed line",
          description: "Construction of industrial production base where food for shelters will be produced on a free basis",
          link: "/project/non-commercial-feed-line",
          bgColor: "rgb(49, 190, 50)"
        },
        {
          title: "Education and Control",
          description: "Lectures on communication, organisation and coordination of processes, control over the use of aid",
          link: "/project/education-and-control",
          bgColor: "rgb(255, 151, 208)"
        },
      ]
    };
  },
  mounted() {
    const controller = new ScrollMagic.Controller();
    
    // Animate each project item on scroll
    this.projects.forEach((_, index) => {
      new ScrollMagic.Scene({
        triggerElement: this.$refs['projectItem' + index][0], 
        triggerHook: 0.8,
        duration: '100%',
        reverse: true,
      })
      .setClassToggle(this.$refs['projectItem' + index][0], "fade-in")
      .addTo(controller);
    });
  },
};
</script>

<style scoped>
.section {
  background-color: #BCF2F6; 
  height: 100vh; 
  display: flex; 
  flex-direction: column; 
  justify-content: center; 
  align-items: center; 
}

.fade-in {
  opacity: 1 !important;
  transform: translateY(0) !important;
  transition: opacity 0.6s ease-out, transform 0.6s ease-out;
}

.collection-item---projects {
  opacity: 0; 
  transform: translateY(30px);
  transition: opacity 0.6s ease-out, transform 0.6s ease-out;
  margin: 20px 0;
  text-align: center; 
  padding: 20px;
  border-radius: 8px; 
}

.project-title {
  color: hsla(0, 0%, 100%, 1);
  font-weight: bold;
}

.small-text-work {
  color: hsla(0, 0%, 100%, 0.7); 
}
</style>
