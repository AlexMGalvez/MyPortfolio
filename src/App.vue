<template>
  <the-canvas/>
  <div id="main">
    <the-description></the-description>
    <the-portfolio></the-portfolio>
	<contact-form></contact-form>
	<div class="spacer"></div>
  </div>
</template>

<script>
import TheCanvas from "./components/TheCanvas.vue";
import TheDescription from "./components/TheDescription.vue";
import ThePortfolio from "./components/ThePortfolio.vue";
import ContactForm from "./components/ContactForm.vue";

export default {
  name: "App",
  components: {
	TheCanvas,
	TheDescription,
	ThePortfolio,
	ContactForm
  },
};
</script>

<style scoped>
@media screen and (max-width: 980px) {
	.spacer {
		height: 150px;
		margin: 0 0 -150px 0;
		background: transparent;
	}
}
</style>