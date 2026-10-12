<template>
  <div class="page home">

    <!-- HERO -->
    <section class="hero">
      <div class="hero-content">
        <p class="eyebrow">Information Technology / Digital Solutions</p>

        <h1>
          Technology that
          <span>moves business forward.</span>
        </h1>

        <p class="hero-description">
          Add a short introduction describing your company,
          what you do and the type of clients you serve.
        </p>

        <div class="hero-actions">
          <button>Explore our services</button>
          <button class="outline">Contact us</button>
        </div>
      </div>

      <p class="scroll-text">
        Scroll to explore ↓
      </p>
    </section>


    <!-- INTRODUCTION -->
    <section class="section intro-section">
      <div class="section-label">
        <span>01</span>
        <p>Who we are</p>
      </div>

      <div class="section-content">
        <h2>
          We use technology to solve
          real business problems.
        </h2>

        <p>
          Replace this text with a brief overview of the company.
          Explain what makes the company different and the value
          it provides to its customers.
        </p>
      </div>
    </section>


    <!-- SERVICES PREVIEW -->
    <section class="section services-preview">
      <div class="section-label">
        <span>02</span>
        <p>What we do</p>
      </div>

      <div class="section-content">
        <h2>Technology expertise.</h2>

        <div class="service-grid">

          <article>
            <span>01</span>
            <h3>IT Infrastructure</h3>
            <p>
              Add a short description of this service.
            </p>
          </article>

          <article>
            <span>02</span>
            <h3>Software Solutions</h3>
            <p>
              Add a short description of this service.
            </p>
          </article>

          <article>
            <span>03</span>
            <h3>IT Support</h3>
            <p>
              Add a short description of this service.
            </p>
          </article>

          <article>
            <span>04</span>
            <h3>Cybersecurity</h3>
            <p>
              Add a short description of this service.
            </p>
          </article>

        </div>
      </div>
    </section>


    <!-- STATISTICS -->
    <section class="stats">

      <div>
        <strong>00+</strong>
        <span>Years Experience</span>
      </div>

      <div>
        <strong>000+</strong>
        <span>Projects Delivered</span>
      </div>

      <div>
        <strong>00+</strong>
        <span>Clients</span>
      </div>

      <div>
        <strong>00</strong>
        <span>Technology Partners</span>
      </div>

    </section>


    <!-- CTA -->
    <section class="cta">
      <p>Have a technology challenge?</p>

      <h2>
        Let's build the
        <span>solution.</span>
      </h2>

      <button>Start a conversation →</button>
    </section>

  </div>
</template>


<style scoped>
  .page {
    width: 100%;
    min-height: 100%;
    background: var(--bg);
    color: var(--text);
  }

  .hero {
    min-height: 100%;
    padding: 9rem 8% 5rem;
    display: flex;
    align-items: center;
    position: relative;
  }

  .hero-content {
    max-width: 1200px;
  }

  .eyebrow,
  .section-label,
  .scroll-text {
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.15em;
  }

  .eyebrow {
    opacity: 0.55;
    margin-bottom: 2rem;
  }

  h1 {
    font-size: clamp(3.5rem, 8vw, 8rem);
    line-height: 0.88;
    letter-spacing: -0.07em;
    font-weight: 500;
    margin: 0;
  }

  h1 span {
    display: block;
    opacity: 0.35;
  }

  .hero-description {
    max-width: 550px;
    margin: 3rem 0 0 auto;
    font-size: 1.1rem;
    line-height: 1.7;
    opacity: 0.7;
  }

  .hero-actions {
    margin-top: 3rem;
    display: flex;
    gap: 1rem;
    justify-content: flex-end;
  }

  button {
    padding: 1rem 1.5rem;
    border: 1px solid white;
    background: white;
    color: #0f172a;
    cursor: pointer;
  }

  button.outline {
    background: transparent;
    color: white;
  }

  .scroll-text {
    position: absolute;
    bottom: 2rem;
    left: 8%;
    opacity: 0.4;
  }

  .section {
    padding: 8rem 8%;
    display: grid;
    grid-template-columns: 180px 1fr;
    gap: 4rem;
    border-top: 1px solid rgba(255, 255, 255, 0.15);
  }

  .section-label {
    opacity: 0.5;
  }

  .section-label span {
    display: block;
    margin-bottom: 1rem;
  }

  .section-content {
    max-width: 1100px;
  }

  .section-content > h2,
  .cta h2 {
    font-size: clamp(2.8rem, 6vw, 6rem);
    line-height: 0.95;
    letter-spacing: -0.05em;
    font-weight: 500;
    margin: 0 0 3rem;
  }

  .section-content > p {
    max-width: 700px;
    font-size: 1.1rem;
    line-height: 1.8;
    opacity: 0.65;
  }

  .services-preview {
    background: var(--bg-soft);
    border-top: 1px solid var(--green);
    border-bottom: 1px solid var(--border);
  }

  .service-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    margin-top: 4rem;
  }

  .service-grid article {
    padding: 2.5rem;
    background: var(--bg);
    border: 1px solid var(--border);
    transition:
      border-color 0.3s ease,
      transform 0.3s ease;
  }

  .service-grid article:hover {
    border-color: var(--green);
    transform: translateY(-4px);
  }

  .service-grid article > span {
    color: var(--green);
  }

  .service-grid h3 {
    font-size: 1.6rem;
    font-weight: 400;
    margin: 2rem 0 1rem;
  }

  .service-grid p {
    opacity: 0.55;
    line-height: 1.6;
  }

  .stats {
    padding: 7rem 8%;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    border-top: 1px solid rgba(255, 255, 255, 0.15);
  }

  .stats div {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .stats strong {
    font-size: clamp(2.5rem, 5vw, 5rem);
    font-weight: 400;
  }

  .stats span {
    font-size: 0.75rem;
    opacity: 0.5;
    text-transform: uppercase;
    letter-spacing: 0.1em;
  }

  .cta {
    min-height: 70vh;
    padding: 8rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    background: var(--bg);
    color: var(--text);
    border-top: 1px solid var(--yellow);
  }

  .cta > p {
    color: var(--yellow);
  }

  .cta h2 span {
    color: var(--green);
    opacity: 1;
  }

  .cta button {
    align-self: flex-start;
    background: #0f172a;
    color: white;
    border-color: #0f172a;
  }

  @media (max-width: 768px) {
    .hero {
      padding: 7rem 1.5rem 4rem;
    }

    h1 {
      font-size: clamp(3rem, 15vw, 6rem);
    }

    .hero-description {
      margin-left: 0;
    }

    .hero-actions {
      justify-content: flex-start;
      flex-wrap: wrap;
    }

    .scroll-text {
      left: 1.5rem;
    }

    .section {
      padding: 6rem 1.5rem;
      grid-template-columns: 1fr;
      gap: 2rem;
    }

    .service-grid {
      grid-template-columns: 1fr;
    }

    .stats {
      padding: 5rem 1.5rem;
      grid-template-columns: repeat(2, 1fr);
      gap: 4rem 2rem;
    }

    .cta {
      padding: 6rem 1.5rem;
    }
  }
</style>