<template>
  <nav class="navbar">
    <div class="container">
      <NuxtLink to="/" class="brand">Charlie Brown</NuxtLink>
      <div class="nav-links">
        <NuxtLink to="/" class="nav-link">Home</NuxtLink>
        <NuxtLink to="/blog" class="nav-link">Blog</NuxtLink>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  background: #fff;
  border-bottom: 1px solid #e6edf3;
  padding: 14px 0;
}

.container {
  max-width: 980px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
}

.brand {
  font-size: 1.2rem;
  font-weight: 700;
  color: #0f172a;
  text-decoration: none;
}

.nav-links {
  display: flex;
  gap: 20px;
}

.nav-link {
  color: #334155;
  text-decoration: none;
  font-weight: 600;
}

.nav-link:hover {
  color: #0ea5a4;
}
</style>
