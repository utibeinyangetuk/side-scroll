<template>
  <div class="page services">

    <!-- HERO -->
    <section class="hero">

      <p class="eyebrow">Services / Capabilities</p>

      <h1>
        What we
        <span>do.</span>
      </h1>

      <p class="lead">
        Add a short description explaining the company's
        technology capabilities and approach to service delivery.
      </p>

    </section>


    <!-- SERVICES -->
    <section class="service-list">

      <article>
        <div class="number">01</div>

        <div class="service-content">
          <h2>IT Infrastructure</h2>

          <p>
            Add an overview of your infrastructure services.
          </p>

          <ul>
            <li>Network Infrastructure</li>
            <li>Server Deployment</li>
            <li>Hardware Solutions</li>
            <li>Cloud Infrastructure</li>
          </ul>
        </div>
      </article>


      <article>
        <div class="number">02</div>

        <div class="service-content">
          <h2>Software Solutions</h2>

          <p>
            Add an overview of your software services.
          </p>

          <ul>
            <li>Business Applications</li>
            <li>Web Applications</li>
            <li>System Integration</li>
            <li>Custom Software</li>
          </ul>
        </div>
      </article>


      <article>
        <div class="number">03</div>

        <div class="service-content">
          <h2>Cybersecurity</h2>

          <p>
            Add an overview of your cybersecurity services.
          </p>

          <ul>
            <li>Security Assessment</li>
            <li>Endpoint Protection</li>
            <li>Network Security</li>
            <li>Security Monitoring</li>
          </ul>
        </div>
      </article>


      <article>
        <div class="number">04</div>

        <div class="service-content">
          <h2>IT Support</h2>

          <p>
            Add an overview of your IT support services.
          </p>

          <ul>
            <li>Technical Support</li>
            <li>System Maintenance</li>
            <li>Remote Support</li>
            <li>IT Consultancy</li>
          </ul>
        </div>
      </article>


      <article>
        <div class="number">05</div>

        <div class="service-content">
          <h2>Cloud Solutions</h2>

          <p>
            Add an overview of your cloud services.
          </p>

          <ul>
            <li>Cloud Migration</li>
            <li>Microsoft 365</li>
            <li>Cloud Backup</li>
            <li>Cloud Management</li>
          </ul>
        </div>
      </article>

    </section>


    <!-- CTA -->
    <section class="cta">
      <p>Need something specific?</p>

      <h2>
        Tell us about your
        technology requirements.
      </h2>

      <button>Contact us →</button>
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
    flex-direction: column;
    justify-content: center;
  }

  .eyebrow {
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    opacity: 0.5;
  }

  h1 {
    margin: 2rem 0;
    font-size: clamp(4rem, 10vw, 10rem);
    line-height: 0.8;
    letter-spacing: -0.07em;
    font-weight: 500;
  }

  h1 span {
    display: block;
    opacity: 0.3;
  }

  .lead {
    max-width: 650px;
    margin-left: auto;
    font-size: 1.15rem;
    line-height: 1.8;
    opacity: 0.7;
  }

  .service-list {
    border-top: 1px solid var(--green);
  }

  .service-list article {
    padding: 5rem 8%;
    display: grid;
    grid-template-columns: 150px 1fr;
    gap: 3rem;
    border-bottom: 1px solid var(--border);
    transition:
      border-color 0.3s ease,
      background 0.3s ease;
  }

  .service-list article:hover {
    background: var(--bg-soft);
    border-bottom-color: var(--green);
  }

  .number {
    color: var(--green);
  }

  .service-content li {
    border-top: 1px solid var(--border);
  }

  .service-content li::before {
    content: "→";
    color: var(--yellow);
    margin-right: 10px;
  }

  .number {
    font-size: 0.7rem;
    opacity: 0.4;
  }

  .service-content {
    max-width: 1000px;
  }

  .service-content h2 {
    margin: 0 0 2rem;
    font-size: clamp(2.5rem, 5vw, 5rem);
    font-weight: 400;
    letter-spacing: -0.04em;
  }

  .service-content > p {
    max-width: 650px;
    line-height: 1.8;
    opacity: 0.6;
  }

  .service-content ul {
    padding: 0;
    margin-top: 3rem;
    list-style: none;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
  }

  .service-content li {
    padding: 1.2rem 0;
    border-top: 1px solid rgba(255, 255, 255, 0.15);
    font-size: 0.85rem;
    opacity: 0.75;
  }

  .cta {
    min-height: 70vh;
    padding: 8rem 8%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    background: var(--bg-soft);
    color: var(--text);
    border-top: 1px solid var(--yellow);
  }

  .cta > p {
    color: var(--yellow);
    opacity: 1;
  }

  .cta button {
    align-self: flex-start;
    padding: 1rem 1.5rem;
    border: 1px solid var(--green);
    background: transparent;
    color: var(--green);
  }

  .cta h2 {
    max-width: 1000px;
    font-size: clamp(3rem, 6vw, 6rem);
    line-height: 0.95;
    letter-spacing: -0.05em;
    font-weight: 500;
  }

  @media (max-width: 768px) {
    .hero {
      padding: 7rem 1.5rem 4rem;
    }

    h1 {
      font-size: clamp(4rem, 20vw, 7rem);
    }

    .lead {
      margin-left: 0;
    }

    .service-list article {
      padding: 4rem 1.5rem;
      grid-template-columns: 1fr;
      gap: 1rem;
    }

    .service-content ul {
      grid-template-columns: 1fr;
    }

    .cta {
      padding: 6rem 1.5rem;
    }
  }
</style>