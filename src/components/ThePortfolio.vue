<template>
  <section id="two">
    <h2>Recent Work</h2>
    <div class="row">
      <article
        class="col-6 col-12-xsmall work-item"
        v-for="(obj, key) in portfolioJSON"
        :key="key"
      >
        <a :href="obj.websiteLink" class="image fit thumb">
          <img :src="'images/thumbs/' + obj.image" alt="" />
        </a>
        <h3>{{ obj.title }}</h3>
        <p>{{ obj.caption }}</p>
        <p id="link">
          Github link:
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
        image: "altrogarden.png",
        title: "Altro Garden",
        caption:
          "This Jamstack application with Vue.js and Gridsome is a website for a small plant nursery to advertise it's stock and take orders for local customers.",
        websiteLink: "https://practical-galileo-92981c.netlify.app/",
        githubLink: "https://github.com/AlexMGalvez/AltroGarden",
      },
      {
        image: "djmichaeltoor.png",
        title: "DJ Michael Toor",
        caption:
          "This DJ website with node.js allows the DJ to advertise himself by presenting his music, bio, personal studio and performed gigs to potential clients.",
        websiteLink: "https://djmichaeltoor.herokuapp.com/",
        githubLink: "https://github.com/AlexMGalvez/DJMichaelToor",
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