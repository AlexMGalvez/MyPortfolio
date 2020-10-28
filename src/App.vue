<template>
  <the-header></the-header>
  <div id="main">
    <the-description></the-description>
    <the-portfolio></the-portfolio>
	<contact-form></contact-form>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheDescription from "./components/TheDescription.vue";
import ThePortfolio from "./components/ThePortfolio.vue";
import ContactForm from "./components/ContactForm.vue";

export default {
  name: "App",
  components: {
	TheHeader,
	TheDescription,
	ThePortfolio,
	ContactForm
  },
};
</script>

