<template>
  <section id="one">
    <header class="major">
      <h1 id="myname">ALEX GALVEZ</h1>
      <h1 id="position">Full Stack Web Developer</h1>
    </header>
    <p>
      As both a university and self taught programmer, my focus in web
      development is on producing sites that not only look good, but function
      well.
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
  </section>
</template>

<style scoped>
#myname {
  background-image: linear-gradient(180deg, rgb(10, 0, 50) 10%, #f0effe 100%);
  font-weight: 800;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

@media screen and (max-width: 1800px) {
  #myname {
    font-size: 68px;
    margin: 0 0 -40px 0;
  }
}

@media screen and (max-width: 490px) {
  #myname {
    font-size: 55px;
    margin: 0 0 -30px 0;
  }
}

#position {
  font-weight: 800;
  color: #f0effe;
  font-family: "Quicksand", sans-serif;
  /* margin-left: 50px; */
}
</style>