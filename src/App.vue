<script setup>
  import { onBeforeUnmount, onMounted, ref } from 'vue';

  import About from '@/views/About.vue';
  import Contact from '@/views/Contact.vue';
  import Home from '@/views/Home.vue';
  import Products from '@/views/Products.vue';
  import Projects from '@/views/Projects.vue';

  const sections = [
    { name: 'Home', number: '01' },
    { name: 'About', number: '02' },
    { name: 'Projects', number: '03' },
    { name: 'Products', number: '04' },
    { name: 'Contact', number: '05' }
  ]

  const container = ref(null)

  const activeSection = ref(0)
  const menuOpen = ref(false)
  const isScrolling = ref(false)


  const goToSection = (index) => {
    if (!container.value) return

    activeSection.value = index
    isScrolling.value = true

    container.value.scrollTo({
      left: index * container.value.clientWidth,
      behavior: 'smooth'
    })

    menuOpen.value = false

    setTimeout(() => {
      isScrolling.value = false
    }, 800)
  }

  const nextSection = () => {
    if (activeSection.value < sections.length - 1) {
      goToSection(activeSection.value + 1)
    }
  }

  const previousSection = () => {
    if (activeSection.value > 0) {
      goToSection(activeSection.value - 1)
    }
  }

  const handleWheel = (event) => {
    if (window.innerWidth <= 768) return

    if (isScrolling.value) {
      event.preventDefault()
      return
    }

    /*
      Find the currently visible panel.

      Each .panel has its own vertical scrollbar.
    */
    const panels = container.value?.querySelectorAll('.panel')

    if (!panels) return

    const currentPanel = panels[activeSection.value]

    if (!currentPanel) return


    /*
      How far the current page has been
      vertically scrolled.
    */
    const scrollTop = currentPanel.scrollTop

    /*
      Total height of everything inside
      the current page.
    */
    const scrollHeight = currentPanel.scrollHeight

    /*
      Visible height of the current page.
    */
    const clientHeight = currentPanel.clientHeight


    /*
      Are we at the top?
    */
    const atTop = scrollTop <= 1


    /*
      Are we at the bottom?

      The 2px tolerance avoids rounding issues.
    */
    const atBottom =
      scrollTop + clientHeight >= scrollHeight - 2


    /*
      SCROLLING DOWN

      If there is still content below us,
      do nothing.

      The browser will perform normal
      vertical scrolling.
    */
    if (event.deltaY > 20) {

      if (!atBottom) {
        return
      }

      /*
        We're already at the bottom.

        Now prevent the normal wheel behavior
        and move horizontally to the next page.
      */
      event.preventDefault()

      nextSection()

      return
    }


    /*
      SCROLLING UP

      If we're not at the top yet,
      allow normal vertical scrolling.
    */
    if (event.deltaY < -20) {

      if (!atTop) {
        return
      }

      /*
        We're at the top.

        Move horizontally back to
        the previous page.
      */
      event.preventDefault()

      previousSection()
    }
  }

  const handleKeydown = (event) => {
    if (event.key === 'ArrowRight' || event.key === 'ArrowDown') {
      nextSection()
    }

    if (event.key === 'ArrowLeft' || event.key === 'ArrowUp') {
      previousSection()
    }

    if (event.key === 'Escape') {
      menuOpen.value = false
    }
  }

  const handleScroll = () => {
    if (!container.value || isScrolling.value) return

    const width = container.value.clientWidth

    if (!width) return

    activeSection.value = Math.round(
      container.value.scrollLeft / width
    )
  }

  const handleResize = () => {
    if (!container.value) return

    container.value.scrollTo({
      left: activeSection.value * container.value.clientWidth,
      behavior: 'auto'
    })
  }

  onMounted(() => {
    const el = container.value

    if (!el) return

    el.addEventListener('wheel', handleWheel, {
      passive: false
    })

    el.addEventListener('scroll', handleScroll)

    window.addEventListener('keydown', handleKeydown)
    window.addEventListener('resize', handleResize)
  })

  onBeforeUnmount(() => {
    const el = container.value

    if (el) {
      el.removeEventListener('wheel', handleWheel)
      el.removeEventListener('scroll', handleScroll)
    }

    window.removeEventListener('keydown', handleKeydown)
    window.removeEventListener('resize', handleResize)
  })
</script>

<template>
  <main class="site-wrapper">

    <!-- Top header -->
    <header class="header">
      <button class="logo" type="button" @click="goToSection(0)">
        LOGO
      </button>

      <div class="header-right">

        <span class="section-indicator">
          0{{ activeSection + 1 }} / 0{{ sections.length }}
        </span>

        <button class="menu-button" type="button" :class="{ active: menuOpen }" :aria-expanded="menuOpen"
          aria-label="Toggle navigation menu" @click="menuOpen = !menuOpen">
          <span></span>
          <span></span>
        </button>

      </div>
    </header>

    <!-- Full-screen menu -->
    <Transition name="menu">
      <nav v-if="menuOpen" class="menu-overlay">
        <div class="menu-content">

          <button v-for="(section, index) in sections" :key="section.name" class="menu-link"
            :class="{ current: activeSection === index }" type="button" @click="goToSection(index)">
            <span class="menu-number">
              {{ section.number }}
            </span>

            <span class="menu-name">
              {{ section.name }}
            </span>

            <span class="menu-arrow">
              →
            </span>
          </button>

        </div>
      </nav>
    </Transition>

    <!-- Side navigation -->
    <nav class="side-nav">
      <button v-for="(section, index) in sections" :key="section.name" type="button" class="side-nav-item"
        :class="{ active: activeSection === index }" @click="goToSection(index)">
        <span class="side-dot"></span>

        <span class="side-label">
          {{ section.name }}
        </span>
      </button>
    </nav>

    <!-- Horizontal scrolling pages -->
    <div ref="container" class="container">
      <section class="panel">
        <Home />
      </section>

      <section class="panel">
        <About />
      </section>

      <section class="panel">
        <Projects />
      </section>

      <section class="panel">
        <Products />
      </section>

      <section class="panel">
        <Contact />
      </section>
    </div>

    <!-- Bottom navigation hint -->
    <div class="scroll-hint">
      <span>SCROLL</span>

      <div class="scroll-line">
        <div class="scroll-progress" :style="{
          width:
            ((activeSection + 1) / sections.length) * 100 + '%'
        }"></div>
      </div>
    </div>

  </main>
</template>

<style scoped>
  * {
    box-sizing: border-box;
  }

  /* =========================================
   APPLICATION SHELL
========================================= */
  .site-wrapper {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: var(--radius);
  }

  /* =========================================
   HEADER
========================================= */
  .header {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 90px;
    padding: 0 3rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    z-index: 1000;
    pointer-events: none;
  }

  .logo,
  .menu-button {
    pointer-events: auto;
  }

  /* LOGO */
  .logo {
    position: relative;
    border: 0;
    padding: 0;
    background: transparent;
    color: var(--text);
    font-size: 1.3rem;
    font-weight: 800;
    letter-spacing: -0.04em;
    cursor: pointer;
  }

  .logo::after {
    content: "";
    position: absolute;
    left: 0;
    bottom: -8px;
    width: 25px;
    height: 2px;
    background: var(--green);
    transition: width 0.3s ease;
  }

  .logo:hover::after {
    width: 100%;
  }

  /* HEADER RIGHT */
  .header-right {
    display: flex;
    align-items: center;
    gap: 2rem;
  }

  .section-indicator {
    color: var(--text-muted);
    font-size: 0.65rem;
    letter-spacing: 0.15em;
    font-weight: 600;
  }

  .section-indicator::first-letter {
    color: var(--green);
  }

  /* =========================================
   MENU BUTTON
========================================= */
  .menu-button {
    width: 52px;
    height: 52px;
    border: 1px solid var(--green);
    border-radius: 50%;
    background: var(--bg);
    color: var(--text);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 6px;
    cursor: pointer;
    transition:
      background 0.3s ease,
      color 0.3s ease,
      border-color 0.3s ease,
      transform 0.3s ease;
  }

  .menu-button span {
    width: 19px;
    height: 1px;
    background: currentColor;
    transition:
      transform 0.3s ease,
      width 0.3s ease;
  }

  .menu-button:hover {
    background: var(--green);
    color: #000;
    transform: scale(1.05);
  }

  .menu-button.active {
    border-color: var(--yellow);
    color: var(--yellow);
  }

  .menu-button.active:hover {
    background: var(--yellow);
    color: #000;
  }

  .menu-button.active span:first-child {
    transform: translateY(3.5px) rotate(45deg);
  }

  .menu-button.active span:last-child {
    transform: translateY(-3.5px) rotate(-45deg);
  }

  /* =========================================
   FULL SCREEN MENU
========================================= */
  .menu-overlay {
    position: absolute;
    inset: 0;
    z-index: 900;
    background: var(--bg);
    color: var(--text);
    display: flex;
    align-items: center;
    padding:
      120px clamp(2rem, 7vw, 8rem) 4rem;
  }

  /* subtle green line */
  .menu-overlay::before {
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 2px;
    background: linear-gradient(90deg,
        var(--green),
        var(--yellow));
  }

  .menu-content {
    width: 100%;
  }

  .menu-link {
    position: relative;
    width: 100%;
    border: 0;
    border-bottom: 1px solid var(--border);
    background: transparent;
    color: var(--text);
    padding: 1rem 0;
    display: grid;
    grid-template-columns:
      60px 1fr auto;
    align-items: center;
    text-align: left;
    cursor: pointer;
    transition:
      border-color 0.3s ease,
      padding 0.3s ease;
  }

  .menu-link:first-child {
    border-top: 1px solid var(--border);
  }

  .menu-link:hover {
    border-color: var(--green);
    padding-left: 1rem;
  }

  .menu-number {
    color: var(--green);
    font-size: 0.65rem;
    letter-spacing: 0.1em;
  }

  .menu-name {
    font-size: clamp(2.8rem, 6vw, 6.5rem);
    line-height: 0.95;
    font-weight: 500;
    letter-spacing: -0.06em;
    transition:
      transform 0.4s ease,
      color 0.3s ease,
      opacity 0.4s ease;
  }

  .menu-arrow {
    color: var(--yellow);
    font-size: 2rem;
    opacity: 0;
    transform: translateX(-20px);
    transition:
      opacity 0.3s ease,
      transform 0.3s ease;
  }

  .menu-link:hover .menu-name {
    color: var(--green);
    transform: translateX(10px);
  }

  .menu-link:hover .menu-arrow {
    opacity: 1;
    transform: translateX(0);
  }

  /* CURRENT PAGE */
  .menu-link.current {
    border-color: var(--yellow);
  }

  .menu-link.current .menu-number {
    color: var(--yellow);
  }

  .menu-link.current .menu-name {
    color: var(--yellow);
  }

  .menu-link.current .menu-arrow {
    color: var(--yellow);
  }

  /* =========================================
   MENU TRANSITION
========================================= */
  .menu-enter-active,
  .menu-leave-active {
    transition:
      opacity 0.45s ease,
      transform 0.45s ease;
  }

  .menu-enter-from,
  .menu-leave-to {
    opacity: 0;
    transform: translateY(-100%);
  }

  /* =========================================
   PAGE CONTAINER
========================================= */
  .container {
    width: 100%;
    height: 100%;
    display: flex;
    overflow-x: auto;
    overflow-y: hidden;
    scroll-snap-type: x mandatory;
    scroll-behavior: smooth;
    scrollbar-width: none;
    overscroll-behavior: none;
    background: var(--bg);
  }

  .container::-webkit-scrollbar {
    display: none;
  }

  /* =========================================
   INDIVIDUAL PAGE
========================================= */
  .panel {
    position: relative;
    width: 100%;
    min-width: 100%;
    height: 100%;
    flex: 0 0 100%;
    overflow-y: auto;
    overflow-x: hidden;
    scroll-snap-align: start;
    scroll-snap-stop: always;
    background: var(--bg);
    scrollbar-width: thin;
    scrollbar-color:
      var(--green) transparent;
  }

  .panel::-webkit-scrollbar {
    width: 4px;
  }

  .panel::-webkit-scrollbar-track {
    background: transparent;
  }

  .panel::-webkit-scrollbar-thumb {
    background: var(--green);
    border-radius: 10px;
  }

  /* =========================================
   SIDE NAVIGATION
========================================= */
  .side-nav {
    position: absolute;
    right: 3rem;
    top: 50%;
    transform: translateY(-50%);
    z-index: 500;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    gap: 1rem;
  }

  .side-nav-item {
    border: 0;
    padding: 0;
    background: transparent;
    color: var(--text-muted);
    display: flex;
    align-items: center;
    flex-direction: row-reverse;
    gap: 0.8rem;
    cursor: pointer;
    transition: color 0.3s ease;
  }

  .side-dot {
    width: 7px;
    height: 7px;
    border: 1px solid var(--text-muted);
    border-radius: 50%;
    transition:
      transform 0.3s ease,
      background 0.3s ease,
      border-color 0.3s ease;
  }

  .side-label {
    font-size: 0.6rem;
    text-transform: uppercase;
    letter-spacing: 0.14em;
    opacity: 0;
    transform: translateX(8px);
    transition:
      opacity 0.3s ease,
      transform 0.3s ease,
      color 0.3s ease;
  }

  .side-nav-item:hover {
    color: var(--green);
  }

  .side-nav-item:hover .side-dot {
    border-color: var(--green);
  }

  .side-nav-item:hover .side-label,
  .side-nav-item.active .side-label {
    opacity: 1;
    transform: translateX(0);
  }

  .side-nav-item.active {
    color: var(--green);
  }

  .side-nav-item.active .side-dot {
    background: var(--green);
    border-color: var(--green);
    transform: scale(1.5);
  }

  /* Alternate yellow active indicator */
  .side-nav-item.active::after {
    content: "";
    width: 15px;
    height: 1px;
    background: var(--yellow);
    position: absolute;
    right: -20px;
  }

  /* =========================================
   SCROLL INDICATOR
========================================= */
  .scroll-hint {
    position: absolute;
    bottom: 2rem;
    left: 3rem;
    z-index: 500;
    display: flex;
    align-items: center;
    gap: 1rem;
    color: var(--text-muted);
    font-size: 0.6rem;
    text-transform: uppercase;
    letter-spacing: 0.15em;
  }

  .scroll-line {
    position: relative;
    width: 100px;
    height: 1px;
    background: var(--border);
    overflow: hidden;
  }

  .scroll-progress {
    height: 100%;
    background: linear-gradient(90deg,
        var(--green),
        var(--yellow));
    transition: width 0.5s ease;
  }

  /* =========================================
   TABLET
========================================= */
  @media (max-width: 1024px) {
    .header {
      padding: 0 2rem;
    }

    .side-nav {
      right: 2rem;
    }

    .scroll-hint {
      left: 2rem;
    }
  }

  /* =========================================
   MOBILE
========================================= */
  @media (max-width: 768px) {
    .header {
      height: 75px;
      padding: 0 1.25rem;
    }

    .logo {
      font-size: 1.1rem;
    }

    .section-indicator {
      display: none;
    }

    .menu-button {
      width: 45px;
      height: 45px;
    }

    .side-nav {
      display: none;
    }

    .container {
      scroll-snap-type: x mandatory;
      touch-action: pan-x pan-y;
    }

    .panel {
      width: 100%;
      min-width: 100%;
      flex-basis: 100%;
    }

    .menu-overlay {
      padding:
        100px 1.5rem 3rem;
    }

    .menu-link {
      grid-template-columns:
        35px 1fr auto;
      padding: 1.1rem 0;
    }

    .menu-link:hover {
      padding-left: 0;
    }

    .menu-name {
      font-size: clamp(2.6rem, 13vw, 4.5rem);
    }

    .scroll-hint {
      left: 1.25rem;
      bottom: 1.5rem;
    }
  }

  /* =========================================
   SMALL PHONE
========================================= */
  @media (max-width: 480px) {
    .menu-name {
      font-size: 2.5rem;
    }

    .menu-number {
      font-size: 0.55rem;
    }

    .scroll-line {
      width: 60px;
    }
  }
</style>