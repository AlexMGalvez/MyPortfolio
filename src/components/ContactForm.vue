<template>
  <flash-message class="messageSent"></flash-message>
  <section id="three">
    <h2 class="title" title="INFORMATION">Contact me</h2>
    <p>
      If you have any enquiries, fill out the form below and you'll receive a
      response promptly.
    </p>
    <div class="row">
      <div class="col-8 col-12-small">
        <form @submit.prevent="sendEmail" id="form1">
          <div class="row gtr-uniform gtr-50">
            <div class="col-6 col-12-xsmall">
              <input
                class="input"
                type="text"
                name="name"
                id="name"
                placeholder="Name"
              />
            </div>
            <div class="col-6 col-12-xsmall">
              <input
                class="input"
                type="email"
                name="email"
                id="email"
                placeholder="Email"
              />
            </div>
            <div class="col-12">
              <textarea
                class="input"
                name="message"
                id="message"
                placeholder="Message"
                rows="4"
              ></textarea>
            </div>
          </div>
        </form>
        <ul class="actions">
          <li><input type="submit" value="Send Message" form="form1" /></li>
        </ul>
      </div>
      <div class="col-4 col-12-small">
        <ul class="labeled-icons">
          <li>
            <h3 class="icon solid fa-home">
              <span class="label">Address</span>
            </h3>
            Kithener, Ontario<br />
            Canada
          </li>
          <li>
            <h3 class="icon solid fa-mobile-alt">
              <span class="label">Phone</span>
            </h3>
            519-502-8307
          </li>
          <li>
            <h3 class="icon solid fa-envelope">
              <span class="label">Email</span>
            </h3>
            <a href="mailto:AlexGalvez@mail.com">AlexGalvez@mail.com</a>
          </li>
          <li>
            <h3 class="icon brands fa-github">
              <span class="label">Github</span>
            </h3>
            <a href="https://github.com/AlexMGalvez">AlexMGalvez</a>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script>
import emailjs from "emailjs-com";

export default {
  methods: {
    sendEmail: (e) => {
      emailjs
        .sendForm(
          "service_oqzssfh",
          "template_4mv15p8",
          e.target,
          "user_pKI4L2oq2PTghoyAoFdLt"
        )
        .then(
          (result) => {
            console.log("SUCCESS!", result.status, result.text);
          },
          (error) => {
            console.log("FAILED...", error);
          }
        );
      e.target.reset();
      alert("Your mail is sent!");
    },
  },
};
</script>

<style scoped>
.input {
  color: #f0effe;
}
</style>