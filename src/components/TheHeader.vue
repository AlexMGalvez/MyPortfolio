<template>
  <header id="header">
    <the-canvas/>
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
  </header>
</template>

<script>
import TheCanvas from "./TheCanvas.vue";

export default {
  name: "Header",
  components: {
    TheCanvas
  },
};
</script>
