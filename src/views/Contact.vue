<template>
  <div class="page contact">

    <!-- CONTACT HERO -->
    <section class="contact-main">

      <div class="heading">

        <p class="eyebrow">
          Contact / Get in touch
        </p>

        <h1>
          Let's talk
          <span>technology.</span>
        </h1>

        <p>
          Tell us about your technology requirements,
          project or business challenge.
        </p>

      </div>


      <!-- FORM -->
      <form class="contact-form">

        <div class="field">
          <label for="name">01 / Name</label>

          <input id="name" type="text" placeholder="Your name" />
        </div>


        <div class="field">
          <label for="email">02 / Email</label>

          <input id="email" type="email" placeholder="you@company.com" />
        </div>


        <div class="field">
          <label for="company">03 / Company</label>

          <input id="company" type="text" placeholder="Company name" />
        </div>


        <div class="field">
          <label for="service">04 / Service</label>

          <select id="service">
            <option>Select a service</option>
            <option>IT Infrastructure</option>
            <option>Software Solutions</option>
            <option>Cybersecurity</option>
            <option>IT Support</option>
            <option>Cloud Solutions</option>
            <option>Other</option>
          </select>
        </div>


        <div class="field">
          <label for="message">
            05 / Tell us about your project
          </label>

          <textarea id="message" rows="5" placeholder="How can we help?"></textarea>
        </div>


        <button type="submit">
          Send enquiry →
        </button>

      </form>

    </section>


    <!-- CONTACT INFORMATION -->
    <section class="contact-info">

      <div>
        <p class="label">Email</p>
        <a href="#">info@yourcompany.com</a>
      </div>

      <div>
        <p class="label">Phone</p>
        <a href="#">+234 XXX XXX XXXX</a>
      </div>

      <div>
        <p class="label">Office</p>

        <address>
          Company Address<br>
          City, State<br>
          Nigeria
        </address>
      </div>

      <div>
        <p class="label">Business Hours</p>

        <p>
          Monday – Friday<br>
          8:00 AM – 5:00 PM
        </p>
      </div>

    </section>


    <!-- FOOTER -->
    <footer>

      <div class="footer-top">

        <h2>
          Your Company
          <span>Name.</span>
        </h2>

        <div class="socials">
          <a href="#">LinkedIn</a>
          <a href="#">Instagram</a>
          <a href="#">Facebook</a>
          <a href="#">X / Twitter</a>
        </div>

      </div>


      <div class="footer-bottom">

        <p>
          © 2026 Your Company. All rights reserved.
        </p>

        <div>
          <a href="#">Privacy</a>
          <a href="#">Terms</a>
        </div>

      </div>

    </footer>

  </div>
</template>


<style scoped>
 .page {
    width: 100%;
    min-height: 100%;
    background: var(--bg);
    color: var(--text);
  }

  .contact-main {
    min-height: 100%;
    padding: 9rem 8% 7rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8rem;
    align-items: center;
  }

  .eyebrow,
  .label {
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    opacity: 0.5;
  }

  .heading h1 {
    margin: 2rem 0;
    font-size: clamp(4rem, 8vw, 8rem);
    line-height: 0.85;
    letter-spacing: -0.07em;
    font-weight: 500;
  }

  .heading h1 span {
    display: block;
    opacity: 0.3;
  }

  .heading > p:last-child {
    max-width: 500px;
    font-size: 1.1rem;
    line-height: 1.7;
    opacity: 0.65;
  }

  .contact-form {
    width: 100%;
  }

  .field {
    padding: 1.5rem 0;
    border-bottom: 1px solid rgba(255, 255, 255, 0.2);
  }

  .field label {
    display: block;
    margin-bottom: 1rem;
    font-size: 0.65rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    opacity: 0.45;
  }

  input,
  select,
  textarea {
    width: 100%;
    border: 0;
    outline: 0;
    background: transparent;
    color: white;
    font: inherit;
    font-size: 1.1rem;
    resize: none;
  }

  input::placeholder,
  textarea::placeholder {
    color: rgba(255, 255, 255, 0.35);
  }

  select {
    color-scheme: dark;
  }

  .contact-form button {
    margin-top: 2.5rem;
    padding: 1rem 1.5rem;
    border: 1px solid white;
    background: white;
    color: #0f172a;
    cursor: pointer;
  }

  .contact-info {
    padding: 7rem 8%;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 3rem;
    background: #dbeafe;
    color: #0f172a;
  }

  .contact-info a {
    color: inherit;
    text-decoration: none;
    font-size: 1rem;
  }

  .contact-info address,
  .contact-info > div > p:last-child {
    font-style: normal;
    line-height: 1.7;
    margin: 0;
  }

  footer {
    padding: 7rem 8% 2rem;
    background: #050914;
  }

  .footer-top {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    gap: 4rem;
    padding-bottom: 6rem;
  }

  .footer-top h2 {
    margin: 0;
    font-size: clamp(3rem, 7vw, 7rem);
    line-height: 0.85;
    letter-spacing: -0.06em;
    font-weight: 500;
  }

  .footer-top h2 span {
    display: block;
    opacity: 0.3;
  }

  .socials {
    display: flex;
    flex-direction: column;
    gap: 0.8rem;
  }

  .socials a,
  .footer-bottom a {
    color: inherit;
    text-decoration: none;
    opacity: 0.6;
  }

  .socials a:hover,
  .footer-bottom a:hover {
    opacity: 1;
  }

  .footer-bottom {
    padding-top: 2rem;
    border-top: 1px solid rgba(255, 255, 255, 0.15);
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 0.7rem;
    opacity: 0.6;
  }

  .footer-bottom div {
    display: flex;
    gap: 2rem;
  }

  @media (max-width: 900px) {
    .contact-main {
      grid-template-columns: 1fr;
      gap: 5rem;
    }
  }

  @media (max-width: 768px) {
    .contact-main {
      padding: 7rem 1.5rem 5rem;
    }

    .heading h1 {
      font-size: clamp(3.5rem, 17vw, 6rem);
    }

    .contact-info {
      padding: 5rem 1.5rem;
      grid-template-columns: repeat(2, 1fr);
    }

    footer {
      padding: 5rem 1.5rem 2rem;
    }

    .footer-top {
      flex-direction: column;
      align-items: flex-start;
    }

    .footer-bottom {
      flex-direction: column;
      align-items: flex-start;
      gap: 1rem;
    }
  }

  @media (max-width: 480px) {
    .contact-info {
      grid-template-columns: 1fr;
    }
  }
</style>