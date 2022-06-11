<template>
  <section id="one">
    <div class="card">
      <header class="major">
        <h1 id="myname">ALEX GALVEZ</h1>
        <h1 id="position">Full Stack Web Developer</h1>
      </header>
      <p>
        A university and self taught programmer with skills ranging from design, performance, security and machine learning.
      </p>
      <!-- <div class="inner">
      <ul class="icons">
        <li>
          <a href="https://github.com/AlexMGalvez" class="icon brands fa-github"
            ><span class="label">Github</span></a
          >
        </li>
        <li>
          <a
            href="mailto:AlexMarkGalvez@hotmail.com"
            class="icon solid fa-envelope"
            ><span class="label">Email</span></a
          >
        </li>
      </ul>
    </div> -->
    </div>
  </section>
</template>

<style scoped>
p {
  color: white;
}

.card {
  position: absolute;
  right: 0px;
  background: #00458B;
  box-shadow: 5px 5px 15px rgba(12, 8, 8, 0.9);
  padding: 30px 48px 10px 200px;
  margin: 0px 0 0px -140px;
  border-radius: 0px 0 0 50px;
}

#myname {
  background-image: linear-gradient(180deg, #2FD2C7 10%, #00458B 100%);
  font-weight: 800;
  font-size: 68px;
  margin: 0 0 -40px 0;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

@media screen and (max-width: 736px) {
  #myname {
    background-image: linear-gradient(180deg, #2FD2C7 0%, #00458B 100%);
    margin: 0 0 -10px 0;
    line-height: 0.8;
  }
}

#position {
  font-weight: 800;
  color: #f0effe;
  font-family: "Quicksand", sans-serif;
}
</style>