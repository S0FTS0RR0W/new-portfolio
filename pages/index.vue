<template>
  <main class="home container">
    <header class="hero" role="banner" aria-labelledby="hero-title">
      <div class="hero-content">
        <h1 id="hero-title">Charlie Brown</h1>
        <p class="lead">Web Developer • System Administrator • Tinkerer</p>
        <p class="tagline">Building dependable systems and delightful web experiences — one small tweak at a time.</p>
        <div class="actions">
          <NuxtLink to="/projects" class="btn primary">View Projects</NuxtLink>
          <a class="btn ghost" href="/contact">Contact</a>
        </div>
      </div>
      <div class="hero-aside" aria-hidden="true">
        <div class="profile-card">
          <div class="avatar" aria-hidden="true">CB</div>
          <ul class="meta">
            <li><strong>Location:</strong> Your City</li>
            <li><strong>Focus:</strong> System Administration, Automation</li>
            <li><strong>Tools:</strong> Vue, Node, Docker, Linux, IDRAC, ILO</li>
          </ul>
        </div>
      </div>
    </header>

    <section class="about" aria-labelledby="about-title">
      <h2 id="about-title">About</h2>
      <p>
        I design and maintain websites and infrastructure, automate routine tasks, and enjoy experimenting with new tools.
        My workflow emphasizes reliability, observability, and maintainable code.
      </p>
    </section>

    <section class="skills" aria-labelledby="skills-title">
      <h2 id="skills-title">Skills</h2>
      <ul>
        <li v-for="skill in skills" :key="skill">{{ skill }}</li>
      </ul>
    </section>

    <section class="featured" aria-labelledby="work-title">
      <h2 id="work-title">Selected Projects</h2>
      <div class="projects-grid">
        <article v-for="p in projects" :key="p.title" class="project">
          <h3>{{ p.title }}</h3>
          <p class="desc">{{ p.desc }}</p>
          <p class="tags">{{ p.tags.join(' • ') }}</p>
          <a v-if="p.link" :href="p.link" class="project-link" target="_blank" rel="noopener">Explore</a>
        </article>
      </div>
      <NuxtLink to="/projects" class="more">See all projects →</NuxtLink>
    </section>

    <section class="contact" aria-labelledby="contact-title">
      <h2 id="contact-title">Contact</h2>
      <p>If you'd like to work together or just say hi, drop a line:</p>
      <a :href="mailtoLink" class="email">{{ email }}</a>
      <div class="socials">
        <a v-for="s in socials" :key="s.name" :href="s.url" target="_blank" rel="noopener">{{ s.name }}</a>
      </div>
    </section>

    <footer class="site-footer" role="contentinfo">
      <small>© {{ year }} Charlie Brown — Web Dev · SysAdmin · Tinkerer</small>
    </footer>
  </main>
</template>

<script setup>
const email = 'charlie@s0fts0rr0w.com'
const mailtoLink = `mailto:${email}`
const year = new Date().getFullYear()

const skills = [
  'Vue 3 & Nuxt',
  'Node.js & TypeScript',
  'Linux & Shell',
  'Docker & Kubernetes',
  'CI/CD & Automation',
  'Monitoring & Observability'
]

const projects = [
  {
    title: 'Portfolio',
    desc: 'This site — minimal, accessible, and statically deployable.',
    tags: ['Nuxt', 'TypeScript', 'Static'],
    link: '/'
  },
  {
    title: 'Infra Automation',
    desc: 'Playbooks and scripts to provision and manage servers reliably.',
    tags: ['Ansible', 'Bash', 'Docker'],
    link: '#'
  },
  {
    title: 'Tooling & Utilities',
    desc: 'Small CLI tools and utilities to speed up daily ops.',
    tags: ['Node', 'Go'],
    link: '#'
  }
]

const socials = [
  { name: 'GitHub', url: 'https://github.com/s0fts0rr0w' },
  { name: 'LinkedIn', url: 'https://linkedin.com/in/s0fts0rr0w' },
  { name: 'Twitter', url: 'https://twitter.com/s0fts0rr0w' }
]
</script>

<style scoped>
.container {
  max-width: 980px;
  margin: 0 auto;
  padding: 28px 20px;
  font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
  color: #0f172a;
}

.hero {
  display: grid;
  grid-template-columns: 1fr 260px;
  gap: 20px;
  align-items: center;
  margin-bottom: 28px;
}

.hero-content h1 {
  margin: 0;
  font-size: 2.2rem;
  letter-spacing: -0.02em;
}

.lead {
  margin: 6px 0 0;
  color: #334155;
  font-weight: 600;
}

.tagline {
  margin: 10px 0 18px;
  color: #475569;
}

.actions .btn {
  display: inline-block;
  margin-right: 10px;
  padding: 8px 14px;
  border-radius: 6px;
  text-decoration: none;
  font-weight: 600;
  border: 1px solid transparent;
}

.btn.primary {
  background: #0ea5a4;
  color: white;
}

.btn.ghost {
  background: transparent;
  border-color: #cbd5e1;
  color: #0f172a;
}

.profile-card {
  background: #f8fafc;
  border-radius: 8px;
  padding: 14px;
  text-align: left;
}

.avatar {
  width: 56px;
  height: 56px;
  border-radius: 8px;
  background: #0ea5a4;
  color: #fff;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  margin-bottom: 10px;
}

.meta {
  list-style: none;
  padding: 0;
  margin: 0;
  font-size: 0.9rem;
  color: #334155;
}

.about, .skills, .featured, .contact {
  margin: 22px 0;
}

.skills ul {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  padding: 0;
  list-style: none;
}

.skills li {
  background: #eef2ff;
  padding: 6px 10px;
  border-radius: 999px;
  font-size: 0.9rem;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 14px;
}

.project {
  border: 1px solid #e6edf3;
  padding: 12px;
  border-radius: 8px;
  background: #fff;
}

.project h3 {
  margin: 0 0 6px;
}

.project .desc {
  color: #475569;
  margin: 0 0 8px;
  font-size: 0.95rem;
}

.project-link {
  color: #0ea5a4;
  text-decoration: none;
  font-weight: 600;
}

.more {
  display: inline-block;
  margin-top: 10px;
  color: #0f172a;
}

.contact .email {
  display: inline-block;
  margin: 6px 0 12px;
  color: #0ea5a4;
  text-decoration: none;
  font-weight: 600;
}

.socials a {
  margin-right: 10px;
  color: #334155;
  text-decoration: none;
}

.site-footer {
  margin-top: 30px;
  padding-top: 18px;
  border-top: 1px solid #e6edf3;
  color: #64748b;
  text-align: center;
  font-size: 0.9rem;
}
</style>