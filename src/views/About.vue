<template>
  <div class="page about">

    <!-- HERO -->
    <section class="hero">
      <p class="eyebrow">About us / Company</p>

      <h1>
        Technology.
        <span>People. Progress.</span>
      </h1>

      <p class="lead">
        Add a strong statement explaining who the company is,
        why it exists and what it believes about technology.
      </p>
    </section>


    <!-- COMPANY STORY -->
    <section class="split-section">

      <div class="section-title">
        <span>01</span>
        <p>Our story</p>
      </div>

      <div class="content">
        <h2>How it started.</h2>

        <p>
          Add your company history here. Explain when the
          company was established, why it was created and
          how it has developed.
        </p>

        <p>
          This section can contain multiple paragraphs,
          allowing you to tell a more complete company story.
        </p>
      </div>

    </section>


    <!-- MISSION / VISION -->
    <section class="mission">

      <article>
        <span>02 / Mission</span>

        <h2>Our mission.</h2>

        <p>
          Add the company's mission statement here.
        </p>
      </article>

      <article>
        <span>03 / Vision</span>

        <h2>Our vision.</h2>

        <p>
          Add the company's vision statement here.
        </p>
      </article>

    </section>


    <!-- VALUES -->
    <section class="values">

      <div class="section-title">
        <span>04</span>
        <p>Our values</p>
      </div>

      <div class="value-list">

        <article>
          <span>01</span>
          <h3>Innovation</h3>
          <p>Add description.</p>
        </article>

        <article>
          <span>02</span>
          <h3>Integrity</h3>
          <p>Add description.</p>
        </article>

        <article>
          <span>03</span>
          <h3>Excellence</h3>
          <p>Add description.</p>
        </article>

        <article>
          <span>04</span>
          <h3>Partnership</h3>
          <p>Add description.</p>
        </article>

      </div>

    </section>


    <!-- TEAM -->
    <section class="team">

      <p class="eyebrow">05 / Our people</p>

      <h2>Meet the team.</h2>

      <div class="team-grid">

        <article v-for="person in 4" :key="person">
          <div class="photo-placeholder">
            Photo
          </div>

          <h3>Team Member</h3>
          <p>Position / Role</p>
        </article>

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
  .section-title {
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.15em;
  }

  .eyebrow {
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
    max-width: 700px;
    margin-left: auto;
    font-size: 1.2rem;
    line-height: 1.8;
  }

  .split-section,
  .values {
    padding: 8rem 8%;
    display: grid;
    grid-template-columns: 180px 1fr;
    gap: 4rem;
    border-top: 1px solid rgba(0, 0, 0, 0.2);
  }

  .section-title {
    opacity: 0.5;
  }

  .content {
    max-width: 850px;
  }

  .content h2,
  .team > h2 {
    font-size: clamp(3rem, 6vw, 6rem);
    line-height: 1;
    letter-spacing: -0.05em;
    font-weight: 500;
    margin: 0 0 3rem;
  }

  .content p {
    max-width: 700px;
    font-size: 1.1rem;
    line-height: 1.8;
    opacity: 0.7;
  }

  .mission {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
  }

  .mission article {
    min-height: 500px;
    padding: 6rem 8%;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    background: var(--bg-soft);
    border: 1px solid var(--border);
    transition:
      border-color 0.3s ease,
      background 0.3s ease;
  }

  .mission article:first-child:hover {
    border-color: var(--green);
  }

  .mission article:last-child:hover {
    border-color: var(--yellow);
  }

  .mission span {
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    opacity: 0.5;
  }

  .mission h2 {
    font-size: clamp(2.5rem, 5vw, 5rem);
    font-weight: 500;
    margin-bottom: 1rem;
  }

  .mission p {
    max-width: 500px;
    line-height: 1.7;
    opacity: 0.65;
  }

  .value-list article {
    padding: 2rem 0;
    display: grid;
    grid-template-columns: 70px 1fr 1fr;
    align-items: center;
    gap: 2rem;
    border-top: 1px solid var(--border);
  }

  .value-list article:hover {
    border-color: var(--green);
  }

  .value-list span {
    color: var(--green);
  }

  .value-list h3 {
    font-size: 1.8rem;
    font-weight: 400;
  }

  .value-list p {
    opacity: 0.6;
  }

  .team {
    padding: 8rem 8%;
    background: var(--bg-soft);
    color: var(--text);
    border-top: 1px solid var(--yellow);
  }

  .photo-placeholder {
    aspect-ratio: 3 / 4;
    background: var(--bg-raised);
    border: 1px solid var(--border);
    display: grid;
    place-items: center;
    color: var(--text-muted);
  }

  .team-grid {
    margin-top: 5rem;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1.5rem;
  }

  .team-grid h3 {
    font-weight: 400;
    margin-bottom: 0.4rem;
  }

  .team-grid p {
    font-size: 0.8rem;
    opacity: 0.5;
  }

  @media (max-width: 768px) {
    .hero {
      padding: 7rem 1.5rem 4rem;
    }

    h1 {
      font-size: clamp(3.5rem, 16vw, 6rem);
    }

    .lead {
      margin-left: 0;
    }

    .split-section,
    .values {
      padding: 6rem 1.5rem;
      grid-template-columns: 1fr;
      gap: 2rem;
    }

    .mission {
      grid-template-columns: 1fr;
    }

    .mission article {
      min-height: 400px;
      padding: 4rem 1.5rem;
    }

    .value-list article {
      grid-template-columns: 40px 1fr;
    }

    .value-list p {
      grid-column: 2;
    }

    .team {
      padding: 6rem 1.5rem;
    }

    .team-grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }
</style>