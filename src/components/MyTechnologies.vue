<template>
<div class="wrapper">
  <div class="card">
    <div class="card-image"><h1 class="icon solid fa-file-code"></h1></div>
    <div class="card-text">
      <h3>FRONT END</h3>
      <p>
        HTML5 | CSS3<br>
        Vue.js | Vuetify

      </p>
    </div>
  </div>
  <div class="card">
    <div class="card-image"><h1 class="icon solid fa-code-branch"></h1></div>
    <div class="card-text">
      <h3>SERVER</h3>
      <p>
        NodeJS<br>
        Express
      </p>
    </div>
  </div>
  <div class="card">
    <div class="card-image"><h1 class="icon solid fa-database"></h1></div>
    <div class="card-text">
      <h3>DATABASE</h3>
      <p>
        MySQL<br>
        GraphQL
      </p>
    </div>
  </div>
  <div class="card">
    <div class="card-image"><h1 class="icon solid fa-cloud"></h1></div>
    <div class="card-text">
      <h3>DEPLOY</h3>
      <p>
       Heroku | Netlify<br>
       Git
      </p>
    </div>
  </div>
  </div>
</template>

<style scoped>
.wrapper {
    margin-top: 80px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.card {
  width: 120px;
  height: 250px;
  display: inline-grid;
  grid-template-columns: 120px;
  grid-template-rows: 100px 250px 80px;
  grid-template-areas: "image" "text";

  background: #31A2AC;
  box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.9);
  text-align: center;
  transition: 0.5s ease;
  margin: 10px;

}



.card-image {
  grid-area: image;
}

.card-image h1 {
    color: rgb(175,28,28);
    font-size: 4em;
}

.card-text {
  grid-area: text;
  margin: 10px;
}

.card-text p {
  color: #F0EFFE;
  font-size: 15px;
  font-weight: 300;
}
.card-text h3 {
  color: #F0EFFE;
  margin-top: 0px;
  /* font-size: 28px; */
}

.card:hover {
  transform: scale(1.15);
  box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.6);
}
</style>