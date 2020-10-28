<template>
  <the-header></the-header>
  <div id="main">
    <the-description></the-description>
    <the-portfolio></the-portfolio>
	<contact-form></contact-form>
  </div>
  <!-- <the-footer></the-footer> -->
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheDescription from "./components/TheDescription.vue";
import ThePortfolio from "./components/ThePortfolio.vue";
import ContactForm from "./components/ContactForm.vue";
//import TheFooter from "./components/TheFooter.vue";

export default {
  name: "App",
  components: {
	TheHeader,
	TheDescription,
	ThePortfolio,
	ContactForm
	//TheFooter
  },
};
</script>

