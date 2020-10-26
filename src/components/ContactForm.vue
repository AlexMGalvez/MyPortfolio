<template>
  <section id="three">
    <h2>Contact me</h2>
    <p>
      If you have any enquiries, fill out the form below and you'll receive a
      response promptly.
    </p>
    <div class="row">
      <div class="col-8 col-12-small">
        <form method="post" action="#">
          <div class="row gtr-uniform gtr-50">
            <div class="col-6 col-12-xsmall">
              <input type="text" name="name" id="name" placeholder="Name" />
            </div>
            <div class="col-6 col-12-xsmall">
              <input type="email" name="email" id="email" placeholder="Email" />
            </div>
            <div class="col-12">
              <textarea
                name="message"
                id="message"
                placeholder="Message"
                rows="4"
              ></textarea>
            </div>
          </div>
        </form>
        <ul class="actions">
          <li><input type="submit" value="Send Message" /></li>
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
            <a href="mailto:AlexMarkGalvez@hotmail.com"
              >AlexMarkGalvez@hotmail.com</a
            >
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>