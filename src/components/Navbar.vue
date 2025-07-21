<template>
  <nav :class="['navbar', { 'visible': isSticky }]">
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#timeline">Education</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      isSticky: false,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      // When user scrolls past the full hero section (100vh), make navbar visible
      this.isSticky = window.scrollY > window.innerHeight - 10;
    },
  },
};
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  padding: 1rem 2rem;
  background: rgba(15, 32, 39, 0.452);
  backdrop-filter: blur(10px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.25);
  transform: translateY(-100%);
  transition: transform 0.3s ease-in-out;
  z-index: 1000;
}

.navbar.visible {
  transform: translateY(0);
}

.nav-links {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 2rem;
  list-style: none;
  margin: 0 auto;
  padding: 0;
  width: 100%;
  max-width: 1200px;
}

.nav-links li {
  list-style: none;
}

.nav-links a {
  text-decoration: none;
  color: #c2e9fb;
  font-weight: bold;
  font-size: 1.1rem;
  transition: color 0.3s;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
}

.nav-links a:hover {
  color: #ffffff;
}

</style>
