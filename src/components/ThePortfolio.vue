<template>
  <section id="two">
    <h2 class="title" title="PORTFOLIO">Recent work</h2>
    <div class="row">
      <template v-for="(obj, key) in portfolioJSON" :key="key">
        <article
          class="col-6 col-12-xsmall work-item"
          
        >
        <div v-bind:class="{ colored: key == 1 || key == 2 || key == 5 }">
          <a :href="obj.websiteLink" class="image fit thumb">
            <img :src="'images/thumbs/' + obj.image" alt="" />
          </a>
          <p>{{ obj.caption }}<br /><br /></p>

          <p>{{ obj.demoText }}</p>
          <div v-if="obj.demo.length != 0">
            <br />
            <a
              v-on:click="toggle(obj.demo)"
              class="button primary small"
              value="Demo"
              >Demo</a
            ><br /><br />
            <div class="demo" :id="obj.demo">
              <video
                :src="'videos/' + obj.demo"
                :id="'video' + obj.demo"
                controls="true"
              ></video>
              <img
                v-on:click="toggle(obj.demo)"
                src="images/close.png"
                class="close"
              />
            </div>
          </div>

          <p>
            Technologies used:<br />
            {{ obj.technologies }}<br /><br />
          </p>
          <p id="link">
            Source Code:
            <a :href="obj.githubLink" class="">{{ obj.githubLink }}</a>
          </p>
          </div>
        </article>
      </template>
    </div>
  </section>
</template>

<script>
export default {
  data: () => ({
    portfolioJSON: [
      {
        image: "wyckoff-ai.png",
        title: "Wyckoff AI",
        caption:
          "An AI-assisted stock trader's financial instrument for executing client-side stock pattern classifications with the use of an LSTM recurrent neural network. The model is currently under development and suffers from under fitting due to a presumable severe lack of training data but shows promising loss function improvements with the expansion of data.",
        websiteLink: "https://wyckoff-ai.netlify.app/",
        githubLink: "https://github.com/AlexMGalvez/wyckoff-ai-website",
        technologies: "Tensorflow.js, Next.js, React, Redux, react-stockcharts, two finance apis",
        demoText: "This demo demonstrates the fetching of financial data, stock chart rendering, pre-trained model loading, and ML pattern classification. Api fetch calls are currently disabled and only dummy data is inputted into the model.",
        demo: "wyckoff-ai.mp4",
      },
      {
        image: "tsm1.png",
        title: "Time Series Math",
        caption:
          "A javascript developer's online resource for mathematically manipulating time series data. This website is a work in progress.",
        websiteLink: "https://timeseriesmathematics.netlify.app/",
        githubLink: "https://github.com/AlexMGalvez/TimeSeriesMathematics",
        technologies: "React, Chart.js",
        demoText: "This demo provides a brief look at the walk-through guide for computing support and resistance lines for time series data. A user interface demonstates the finished result.",
        demo: "tsm1.mp4",
      },
      {
        image: "altro-garden2.png",
        title: "Altro Garden",
        caption:
          "A jamstack powered e-commerce platform for a plant nursery to advertise it's stock and take orders for local customers.",
        websiteLink: "https://altrogarden.netlify.app/",
        githubLink: "https://github.com/AlexMGalvez/AltroGarden",
        technologies:
          "Vue.js, Gridsome, Strapi CMS, Vuetify, GraphQL, Snipcart, MongoDB",
        demoText:
          "This demo is a brief look into cart usage, product search queries, and checkout.",
        demo: "altrogarden1.mp4",
      },
      {
        image: "djmichaeltoor.png",
        title: "DJ Michael Toor",
        caption:
          "A Cambridge DJ's website which allows him to advertise himself by presenting his music, bio, personal studio and performed gigs to potential clients.",
        websiteLink: "https://djmichaeltoor.herokuapp.com/",
        githubLink: "https://github.com/AlexMGalvez/DJMichaelToor",
        technologies: "NodeJS, Express, MySQL, Bootstrap4",
        demoText:
          "This demo is a look into the custom-built content management system, database manipulation, and administrator options. Admin authentication and authorization is demonstrated.",
        demo: "djmichaeltoor1.mp4",
      },
    ],
  }),
  methods: {
    toggle: (demoObj) => {
      let demo = document.getElementById(demoObj);
      demo.classList.toggle("active");
      let video = document.getElementById("video" + demoObj);
      video.classList.toggle("active");
      video.pause();
      video.currentTime = 0;
    },
  },
};
</script>

<style scoped>
#link {
  margin-top: 8px;

  text-overflow: ellipsis;

  /* Needed to make it work */
  overflow: hidden;
  white-space: nowrap;
}

.colored {
  background-color: #00458b;
  padding: 20px;
  box-shadow: 5px 5px 15px rgba(97, 79, 79, 0.9);
  border-radius: 0px 0 0 50px;
}

.colored p {
  color: white;
}

.colored a {
  color: #2FD2C7;
}

.demo {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 10000;
  background: rgba(0, 0, 0, 0.95);
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  visibility: hidden;
  opacity: 0;
}

.demo.active {
  visibility: visible;
  opacity: 1;
}

.demo video {
  position: relative;
  max-width: 900px;
  outline: none;
}

.close {
  position: absolute;
  top: 30px;
  right: 30px;
  cursor: pointer;
  filter: invert(1);
  max-width: 32px;
}

@media (max-width: 991px) {
  .demo video {
    max-width: 90%;
  }
}
</style>
