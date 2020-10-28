<template>
  <section id="two">
    <h2>Recent Work</h2>
    <div class="row">
      <article class="col-6 col-12-xsmall work-item" v-for="(obj, key) in portfolioJSON" :key="key">
        <a :href="obj.websiteLink" class="image fit thumb">
            <img :src="'images/thumbs/' + obj.image" alt="">
        </a>
        <h3>{{ obj.title }}</h3>
        <p>{{ obj.caption }}</p>
        <p id="link">Github link: <a :href="obj.githubLink" class="">{{ obj.githubLink }}</a></p>
      </article>
    </div>
  </section>
</template>

<script>
export default {
    data: () => ({
        portfolioJSON: [
            {
                image: 'djmichaeltoor.png',
                title: 'DJ Michael Toor',
                caption: 'As my first full stack project with node.js, this dj website allows the dj to advertise himself by presenting his music, bio, personal studio and his performed gigs to potential clients.',
                websiteLink: 'https://djmichaeltoor.herokuapp.com/',
                githubLink: 'https://github.com/AlexMGalvez/DJMichaelToor'
            }
        ]
    })
};
</script>

<style scoped>
#link {
  margin-top: 8px;
}
</style>