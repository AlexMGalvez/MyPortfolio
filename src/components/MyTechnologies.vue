<template>
<h2 class="title" title="TECHNOLOGIES">My skills</h2>
<div class="wrapper">
  <div class="card">
    <div class="card-image"><h1 class="icon solid fa-file-code"></h1></div>
    <div class="card-text">
      <h3>FRONT END</h3>
      <p>
        Javascript<br>
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
        MongoDB<br>
        GraphQL
      </p>
    </div>
  </div>
  <div class="card">
    <div class="card-image"><h1 class="icon solid fa-cloud"></h1></div>
    <div class="card-text">
      <h3>DEPLOY</h3>
      <p>
       Heroku<br>
       Netlify<br>
       Git
      </p>
    </div>
  </div>
  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.title {
  margin-top: 100px;
  padding-top: 230px;
}

.card {
  width: 120px;
  height: 260px;
  display: inline-grid;
  grid-template-columns: 120px;
  grid-template-rows: 100px 260px 80px;
  grid-template-areas: "image" "text";

  background: rgb(25,0,97);
  box-shadow: 5px 5px 15px rgba(0,0,0, 0.9);
  text-align: center;
  transition: 0.5s ease;
  margin: 10px;

}

.card-image {
  grid-area: image;
}

.card-image h1 {
    color: #F0EFFE;
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
  font-size: 18px;
}

.card:hover {
  transform: scale(1.15);
  box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.6);
}

@media screen and (max-width: 500px) {
.title {
  padding-top: 330px;
}
}
</style>