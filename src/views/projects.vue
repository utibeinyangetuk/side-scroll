<template>
  <div class="page solutions">

    <!-- HERO -->
    <section class="hero">

      <p class="eyebrow">Solutions / Our work</p>

      <h1>
        Technology
        <span>in action.</span>
      </h1>

      <p class="lead">
        Showcase the solutions, projects and technologies
        your company has delivered.
      </p>

    </section>


    <!-- PROJECTS -->
    <section class="projects">

      <p class="section-label">
        01 / Selected projects
      </p>


      <article class="project">

        <div class="project-number">01</div>

        <div class="project-image">
          Project Image
        </div>

        <div class="project-info">
          <p>Infrastructure / 2026</p>

          <h2>Project Name</h2>

          <p>
            Add a brief description explaining the client's
            problem and the solution delivered.
          </p>

          <button>View project →</button>
        </div>

      </article>


      <article class="project">

        <div class="project-number">02</div>

        <div class="project-image">
          Project Image
        </div>

        <div class="project-info">
          <p>Software / 2026</p>

          <h2>Project Name</h2>

          <p>
            Add a brief description explaining the client's
            problem and the solution delivered.
          </p>

          <button>View project →</button>
        </div>

      </article>


      <article class="project">

        <div class="project-number">03</div>

        <div class="project-image">
          Project Image
        </div>

        <div class="project-info">
          <p>Cloud / 2026</p>

          <h2>Project Name</h2>

          <p>
            Add a brief description explaining the client's
            problem and the solution delivered.
          </p>

          <button>View project →</button>
        </div>

      </article>

    </section>


    <!-- TECHNOLOGIES -->
    <section class="technologies">

      <p class="section-label">
        02 / Technologies
      </p>

      <h2>
        Technology we
        work with.
      </h2>

      <div class="tech-grid">

        <div>Microsoft</div>
        <div>Cisco</div>
        <div>Cloud</div>
        <div>Networking</div>
        <div>Security</div>
        <div>Software</div>
        <div>Database</div>
        <div>Hardware</div>

      </div>

    </section>


    <!-- INDUSTRIES -->
    <section class="industries">

      <p class="section-label">
        03 / Industries
      </p>

      <div class="industry-list">
        <span>Finance</span>
        <span>Education</span>
        <span>Healthcare</span>
        <span>Government</span>
        <span>Retail</span>
        <span>Professional Services</span>
      </div>

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

  .eyebrow,
  .section-label {
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    opacity: 0.5;
  }

  h1 {
    margin: 2rem 0;
    font-size: clamp(4rem, 9vw, 9rem);
    line-height: 0.85;
    letter-spacing: -0.07em;
    font-weight: 500;
  }

  h1 span {
    display: block;
    opacity: 0.3;
  }

  .lead {
    max-width: 600px;
    margin-left: auto;
    font-size: 1.15rem;
    line-height: 1.8;
  }

  .projects {
    padding: 8rem 8%;
    background: var(--bg);
    color: var(--text);
    border-top: 1px solid var(--green);
  }

  .project {
    padding: 5rem 0;
    display: grid;
    grid-template-columns: 60px 1.2fr 1fr;
    gap: 3rem;
    border-bottom: 1px solid var(--border);
  }

  .project-number {
    font-size: 0.7rem;
    opacity: 0.4;
    color: var(--green);
  }

  .project-image {
    min-height: 400px;
    background: var(--bg-raised);
    border: 1px solid var(--border);
    display: grid;
    place-items: center;
    color: var(--text-muted);
  }

  .project-info {
    align-self: center;
  }

  .project-info > p:first-child {
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    opacity: 0.4;
  }

  .project-info h2 {
    font-size: clamp(2rem, 4vw, 4rem);
    font-weight: 400;
    letter-spacing: -0.04em;
    margin: 1rem 0 2rem;
  }

  .project-info > p {
    line-height: 1.7;
    opacity: 0.6;
  }

  .project-info button {
    margin-top: 2rem;
    padding: 0;
    border: 0;
    background: transparent;
    color: white;
    cursor: pointer;
  }

  .technologies {
    padding: 8rem 8%;
  }

  .technologies h2 {
    max-width: 900px;
    font-size: clamp(3rem, 6vw, 6rem);
    line-height: 0.95;
    letter-spacing: -0.05em;
    font-weight: 500;
  }

  .tech-grid {
    margin-top: 5rem;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
  }

  .tech-grid div {
    aspect-ratio: 1;
    border: 1px solid rgba(0, 0, 0, 0.15);
    display: grid;
    place-items: center;
    font-size: 0.8rem;
  }

  .industries {
    padding: 8rem 8%;
    background: #dbeafe;
  }

  .industry-list {
    margin-top: 4rem;
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
  }

  .industry-list span {
    padding: 1rem 1.5rem;
    border: 1px solid rgba(0, 0, 0, 0.3);
    border-radius: 100px;
  }

  @media (max-width: 768px) {
    .hero {
      padding: 7rem 1.5rem 4rem;
    }

    h1 {
      font-size: clamp(3.5rem, 17vw, 6rem);
    }

    .lead {
      margin-left: 0;
    }

    .projects {
      padding: 6rem 1.5rem;
    }

    .project {
      grid-template-columns: 1fr;
      gap: 1.5rem;
    }

    .project-image {
      min-height: 300px;
    }

    .technologies,
    .industries {
      padding: 6rem 1.5rem;
    }

    .tech-grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }
</style>