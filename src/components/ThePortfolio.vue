<template>
  <section id="two">
    <h2 class="title" title="PORTFOLIO">Recent work</h2>
    <div class="row">
      <article
        class="col-6 col-12-xsmall work-item"
        v-for="(obj, key) in portfolioJSON"
        :key="key"
      >
        <a :href="obj.websiteLink" class="image fit thumb">
          <img :src="'images/thumbs/' + obj.image" alt="" />
        </a>
        <!-- <h3>{{ obj.title }}</h3> -->
        <p>{{ obj.caption }}<br><br></p>
        <p>Technologies used:<br> {{ obj.technologies }}</p>
        <p id="link">
          Source Code:
          <a :href="obj.githubLink" class="">{{ obj.githubLink }}</a>
        </p>
      </article>
    </div>
  </section>
</template>

<script>
export default {
  data: () => ({
    portfolioJSON: [
      {
        image: "altro-garden3.png",
        title: "Altro Garden",
        caption:
          "This front-end focused project is a Jamstack powered website for a small plant nursery to advertise it's stock and take orders for local customers.",
        websiteLink: "https://altrogarden.netlify.app/",
        githubLink: "https://github.com/AlexMGalvez/AltroGarden",
        technologies: "Vue.js, Gridsome, Strapi CMS, Vuetify, GraphQL, MongoDB"
      },
      {
        image: "djmichaeltoor.png",
        title: "DJ Michael Toor",
        caption:
          "This back-end focused project is a DJ website which allows the DJ to advertise himself by presenting his music, bio, personal studio and performed gigs to potential clients.",
        websiteLink: "https://djmichaeltoor.herokuapp.com/",
        githubLink: "https://github.com/AlexMGalvez/DJMichaelToor",
        technologies: "NodeJS, Express, MySQL, Bootstrap4"
      },
    ],
  }),
};
</script>

<style scoped>
#link {
  margin-top: 8px;
}
</style>