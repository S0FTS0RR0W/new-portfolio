<template>
    <div class="contact container">
        <h1>Contact</h1>
        <p>If you'd like to work together or just say hi, drop a line:</p>
        <a :href="mailtoLink" class="email">{{ email }}</a>
    </div>
</template>

<script setup>
const email = 'charlie@s0fts0rr0w.com'
const mailtoLink = `mailto:${email}`
</script>

<style scoped>
.container {
    max-width: 980px;
    margin: 0 auto;
    padding: 28px 20px;
    color: var(--text-color);
}

.email {
    color: var(--primary-color);
    text-decoration: none;
    font-weight: 600;
}
</style>