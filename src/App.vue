<template>
  <div class="site-shell">
    <header class="nav-wrap fixed">
      <nav class="nav container">
        <a class="brand" href="#home"><span>Pranto</span><b>Deb</b></a>
        <button class="menu-btn" @click="mobileOpen = !mobileOpen" :aria-label="mobileOpen ? 'Close menu' : 'Open menu'">
          <span></span>
          <span></span>
          <span></span>
        </button>
        <div class="nav-links" :class="{ open: mobileOpen }">
          <a href="#projects" @click="mobileOpen=false">Projects</a>
          <a href="#experience" @click="mobileOpen=false">Experience</a>
          <a href="#skills" @click="mobileOpen=false">Skills</a>
          <a href="#services" @click="mobileOpen=false">Services</a>
          <a href="#contact" @click="mobileOpen=false">Contact</a>
          <a class="nav-cta" :href="profile.whatsapp" target="_blank">Hire Me</a>
        </div>
      </nav>
    </header>

    <main id="home">
      <section class="hero container reveal">
        <div class="hero-copy">
          <p class="eyebrow">Laravel • Vue.js • Full Stack Developer</p>
          <h1>Building scalable web & mobile applications for businesses that need speed, trust, and growth.</h1>
          <p class="lead">I’m Pranto Deb, a Full Stack Laravel & Vue.js Developer with 3.5+ years of professional experience. I help startups, agencies, and businesses build fast, secure, responsive, and production-ready web applications, dashboards, APIs, and mobile app publishing solutions.</p>
          <div class="hero-actions">
            <a class="btn primary" :href="profile.whatsapp" target="_blank">Hire Me</a>
            <a class="btn secondary" href="#projects">View Projects</a>
            <a class="btn secondary" href="/Pranto-Deb-CV.pdf" target="_blank">Download CV</a>
          </div>
          <div class="social-row">
            <a href="https://github.com/Pranto-Deb" target="_blank">GitHub</a>
            <a href="https://www.linkedin.com/in/pranto-deb" target="_blank">LinkedIn</a>
            <a href="https://www.facebook.com/prantodeb23" target="_blank">Facebook</a>
            <a :href="profile.whatsapp" target="_blank">WhatsApp</a>
          </div>
        </div>

        <div class="hero-card">
          <div class="profile-panel">
            <img src="/pranto-deb.jpg" alt="Pranto Deb" />
            <div>
              <h3>Pranto Deb</h3>
              <p>Software Engineer</p>
              <small>Dhaka, Bangladesh</small>
            </div>
          </div>
          <div class="metric-grid">
            <div><strong>3.5+</strong><span>Years Experience</span></div>
            <div><strong>24+</strong><span>Projects Delivered</span></div>
            <div><strong>Full Stack Dev</strong><span>Web & Mobile Apps</span></div>
          </div>
          <div class="availability-card">
            <span></span>
            Available for Laravel, Vue.js, API, dashboard, business website, and mobile app launch projects. Open to Fiverr, Upwork, and long-term client collaborations.
          </div>
        </div>
      </section>

      <section class="logo-strip reveal">
        <div class="container strip-inner">
          <span>Laravel Developer</span><span>Vue.js Developer</span><span>Full Stack Developer</span><span>PHP</span><span>Tailwind CSS</span><span>Bootstrap</span><span>MySQL</span><span>REST API</span><span>API Integration</span><span>WordPress</span><span>Git</span><span>Mobile App Publishing</span>
        </div>
      </section>

      <section class="section container reveal" id="projects">
        <div class="section-head">
          <p class="eyebrow">Selected Work</p>
          <h2>Real projects built for healthcare, fintech, booking, travel, and business platforms.</h2>
          <p>A selection of live websites and app launch work showing my ability to design, develop, deploy, and maintain production-ready digital products.</p>
        </div>

        <div class="projects-grid premium-projects">
          <article v-for="project in projects" :key="project.name" class="project-card">
            <div class="project-image-wrap" :class="{ 'app-preview-wrap': project.isApp }">
              <img :src="project.image" :alt="project.name + ' project preview'" />
              <div class="project-overlay">
                <a :href="project.link" target="_blank">{{ project.action }}</a>
              </div>
            </div>

            <div class="project-top">
              <span>{{ project.type }}</span>
              <a :href="project.link" target="_blank">{{ project.cta }} →</a>
            </div>
            <h3>{{ project.name }}</h3>
            <p>{{ project.desc }}</p>
            <div class="tags"><span v-for="tag in project.tags" :key="tag">{{ tag }}</span></div>
          </article>
        </div>
      </section>

      <section class="section soft reveal" id="experience">
        <div class="container two-col">
          <div class="section-head left sticky-copy">
            <p class="eyebrow">Experience</p>
            <h2>3.5+ years of professional full stack development experience.</h2>
            <p>I have worked on healthcare platforms, fintech websites, booking systems, admin dashboards, responsive frontend interfaces, Laravel backend systems, debugging, app publishing workflows, and long-term production maintenance.</p>
          </div>
          <div class="timeline">
            <div v-for="job in jobs" :key="job.company" class="timeline-item">
              <span class="dot"></span>
              <p class="period">{{ job.period }}</p>
              <h3>{{ job.title }}</h3>
              <h4>{{ job.company }}</h4>
              <p class="location">{{ job.location }}</p>
              <ul><li v-for="item in job.points" :key="item">{{ item }}</li></ul>
            </div>
          </div>
        </div>
      </section>

      <section class="section container reveal" id="skills">
        <div class="section-head">
          <p class="eyebrow">Technical Skills</p>
          <h2>Laravel, Vue.js, API, database, deployment, and mobile app publishing skills.</h2>
        </div>
        <div class="skill-grid">
          <div v-for="skill in skills" :key="skill.title" class="skill-card">
            <h3>{{ skill.title }}</h3>
            <p>{{ skill.text }}</p>
          </div>
        </div>
      </section>

      <section class="section container reveal" id="services">
        <div class="section-head">
          <p class="eyebrow">Services</p>
          <h2>Services I offer for Fiverr, Upwork, and direct clients.</h2>
          <p>Clear, practical development services for business owners, startups, agencies, and teams that need reliable web and mobile app solutions.</p>
        </div>
        <div class="service-grid">
          <div v-for="service in services" :key="service.title" class="service-card">
            <div class="icon">{{ service.icon }}</div>
            <h3>{{ service.title }}</h3>
            <p>{{ service.text }}</p>
          </div>
        </div>
      </section>

      <section class="section container reveal">
        <div class="conversion-card">
          <div>
            <p class="eyebrow">Hire a Developer</p>
            <h2>Need a reliable full stack developer for your next project?</h2>
            <p>I can help you build Laravel web apps, Vue.js frontends, admin dashboards, REST APIs, booking systems, business websites, and mobile app publishing workflows with clean, scalable, and maintainable code.</p>
          </div>
          <div class="conversion-actions">
            <a class="btn primary" :href="profile.whatsapp" target="_blank">Hire Me on WhatsApp</a>
            <a class="btn secondary" href="mailto:prantodeb1@gmail.com">Email Me</a>
          </div>
        </div>
      </section>

      <section class="section contact-section reveal" id="contact">
        <div class="container contact-grid">
          <div>
            <p class="eyebrow">Contact</p>
            <h2>Let’s discuss your project.</h2>
            <p>Send me your idea, website issue, Figma design, dashboard requirement, API task, or app publishing plan. I’ll help you choose the right technical solution and build it professionally.</p>
          </div>
          <div class="contact-card">
            <a href="mailto:prantodeb1@gmail.com"><b>Email</b><span>prantodeb1@gmail.com</span></a>
            <a :href="profile.whatsapp" target="_blank"><b>WhatsApp</b><span>+8801811172693</span></a>
            <a href="https://www.linkedin.com/in/pranto-deb" target="_blank"><b>LinkedIn</b><span>linkedin.com/in/pranto-deb</span></a>
            <a href="https://github.com/Pranto-Deb" target="_blank"><b>GitHub</b><span>github.com/Pranto-Deb</span></a>
          </div>
        </div>
      </section>
    </main>

    <footer class="footer">
      <div class="container footer-inner">
        <p>© {{ new Date().getFullYear() }} Pranto Deb. Full Stack Laravel & Vue.js Developer.</p>
        <a :href="profile.whatsapp" target="_blank">WhatsApp</a>
      </div>
    </footer>

    <a class="floating-whatsapp" :href="profile.whatsapp" target="_blank" aria-label="Chat on WhatsApp">
      <svg viewBox="0 0 32 32" aria-hidden="true">
        <path d="M16.02 3.2A12.7 12.7 0 0 0 5.05 22.33L3.5 28.8l6.62-1.73A12.72 12.72 0 1 0 16.02 3.2Zm0 22.97a10.2 10.2 0 0 1-5.2-1.42l-.37-.22-3.92 1.03 1.04-3.82-.25-.39A10.17 10.17 0 1 1 16.02 26.17Zm5.59-7.64c-.31-.16-1.84-.91-2.13-1.01-.29-.11-.5-.16-.71.16-.21.31-.82 1.01-1 1.22-.18.21-.37.23-.68.08-.31-.16-1.32-.49-2.52-1.56-.93-.83-1.56-1.85-1.74-2.16-.18-.31-.02-.48.14-.64.14-.14.31-.37.47-.55.16-.18.21-.31.31-.52.1-.21.05-.39-.03-.55-.08-.16-.71-1.7-.97-2.33-.26-.61-.52-.53-.71-.54h-.61c-.21 0-.55.08-.84.39-.29.31-1.1 1.07-1.1 2.62s1.13 3.04 1.29 3.25c.16.21 2.23 3.4 5.4 4.77.75.32 1.34.52 1.8.66.76.24 1.45.21 2 .13.61-.09 1.84-.75 2.1-1.48.26-.73.26-1.36.18-1.49-.08-.13-.29-.21-.6-.37Z"/>
      </svg>
    </a>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue'

const mobileOpen = ref(false)
const profile = { whatsapp: 'https://wa.me/8801811172693' }

const projects = [
  { name: 'Shotayu Web Platform', type: 'Healthcare Platform', image: '/images/shotayu.png', link: 'https://shotayu.com/', action: 'Visit Website', cta: 'Live', desc: 'Full-featured telemedicine platform with doctor-patient workflows, appointment booking, provider access, healthcare operations, and scalable production architecture.', tags: ['Laravel', 'Vue.js', 'Healthcare'] },
  { name: 'Shotayu Android App', type: 'Published Android App', image: '/images/shotayu-playstore-preview.png', link: 'https://play.google.com/store/apps/details?id=com.shotayu.app', action: 'View on Google Play', cta: 'Play Store', isApp: true, desc: 'Published healthcare Android app with patient workflow, appointment access, vitals, medicine ordering, family health tracking, and Google Play release support.', tags: ['Android App', 'Google Play', 'Publishing'] },
  { name: 'Klik Moris', type: 'Tour ERP', image: '/images/klik-moris.png', link: 'https://klikmoris.com/', action: 'Visit Project', cta: 'Live', desc: 'Travel and tour ERP platform for hotels, transfers, tours, activities, and booking-focused business operations with a clean customer experience.', tags: ['PHP', 'Laravel', 'Booking'] },
  { name: 'DoctorVenue', type: 'Doctor Booking', image: '/images/doctor-venue.png', link: 'https://doctorvenue.com/', action: 'Visit Project', cta: 'Live', desc: 'Doctor and hospital booking platform with search, doctor profiles, appointment-focused UI, responsive layouts, and patient-friendly navigation.', tags: ['Laravel', 'UI', 'Responsive'] },
  { name: 'PNRFR', type: 'Non-profit Website', image: '/images/pnrfr.png', link: 'https://pnrfr.com/', action: 'Visit Project', cta: 'Live', desc: 'Professional non-profit website with bilingual page structure, foundation story, donation CTAs, leadership content, and trust-building design.', tags: ['WordPress', 'UI', 'Content'] },
  { name: 'The Sports Arena', type: 'Sports Booking', image: '/images/sports-arena.png', link: 'https://thesportsarena.xyz/', action: 'Visit Project', cta: 'Live', desc: 'Sports facility booking and management website built for playground discovery, event information, user conversion, and modern sports branding.', tags: ['Laravel', 'System', 'Booking'] },
  { name: 'XyloPay', type: 'Fintech Website', image: '/images/xylopay.png', link: 'https://xylopay.io/', action: 'Visit Project', cta: 'Live', desc: 'Premium fintech website for an online payment company with modern landing page design, strong CTA flow, and performance-focused UI.', tags: ['Laravel', 'Fintech', 'Landing Page'] }
]

const jobs = [
  { title: 'Software Engineer', company: 'Medisquare Health · Full-time', period: 'Nov 2022 - Present', location: 'Dhaka, Bangladesh · Hybrid', points: ['Designing and developing modern websites with modern technologies and frameworks.', 'Developing and maintaining healthcare platforms, doctor/patient workflows, and responsive dashboards.', 'Supporting Android app publishing and Google Play release workflow for healthcare app products.', 'Modifying and making changes according to business requirements.', 'Checking for errors, debugging websites, and improving production stability.', 'Making websites responsive across desktop, tablet, and mobile devices.', 'Communicating with users and stakeholders about project requirements.'] },
  { title: 'Web Developer', company: 'Bangla Puzzle Limited · Full-time', period: 'Nov 2021 - Oct 2022', location: 'Dhaka, Bangladesh · On-site', points: ['Designed and developed modern websites with modern technologies and frameworks.', 'Converted PSD/XD/Figma designs into HTML, Bootstrap, and Tailwind CSS.', 'Modified and improved projects according to requirements.', 'Debugged websites and fixed frontend/backend issues.', 'Built responsive interfaces and communicated with users about project needs.'] },
  { title: 'Web Application Developer Intern', company: 'Brainchild Software', period: 'May 2021 - Sep 2021', location: 'Ring Road, Shyamoli, Dhaka', points: ['Designed modern websites and frontend layouts.', 'Worked on backend development and website maintenance.', 'Created frontend design with Bootstrap and Tailwind CSS.', 'Checked errors and debugged websites during development.'] }
]

const skills = [
  { title: 'Laravel Backend Development', text: 'Laravel, PHP, MySQL database structure, authentication, CRUD, REST API development, API integration, and scalable business logic.' },
  { title: 'Vue.js Frontend Development', text: 'Vue.js, JavaScript, HTML, CSS, Bootstrap, Tailwind CSS, responsive UI, reusable components, and modern frontend workflows.' },
  { title: 'App Development & Publishing', text: 'Android app publishing, Google Play Store release support, webview app workflow, app listing preparation, and production launch support.' },
  { title: 'Professional Delivery', text: 'Git version control, team collaboration, debugging, requirement analysis, deployment support, client communication, and long-term maintenance.' },
]

const services = [
  { icon: '01', title: 'Laravel Web Applications', text: 'Custom Laravel applications, admin dashboards, booking systems, SaaS-style platforms, and scalable backend architecture.' },
  { icon: '02', title: 'Vue.js Frontend Development', text: 'Modern Vue.js interfaces with smooth UX, reusable components, responsive layouts, and clean frontend structure.' },
  { icon: '03', title: 'Business Website Development', text: 'Corporate, portfolio, healthcare, booking, fintech, and service websites designed for speed, trust, and conversion.' },
  { icon: '04', title: 'REST API & Database', text: 'REST API development, third-party API integration, MySQL database design, authentication, and dashboard workflows.' },
  { icon: '05', title: 'Mobile App Publishing', text: 'Google Play publishing support, app listing setup, release preparation, webview app workflow, and launch assistance.' },
  { icon: '06', title: 'WordPress Customization', text: 'Professional WordPress sites, page structure, multilingual setup, and theme customization.' },
  { icon: '07', title: 'Bug Fixing & Optimization', text: 'Website bug fixing, performance optimization, deployment support, responsive issue fixing, and long-term maintenance.' }
]

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) entry.target.classList.add('show')
    })
  }, { threshold: 0.12 })
  document.querySelectorAll('.reveal').forEach(el => observer.observe(el))
})
</script>
