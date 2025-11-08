<template>
  <header class="header">
    <nav class="nav">
      <div class="logo-section">
        <router-link to="/" class="logo-link">
          <img src="@/assets/devfest-indore-header-logo.png" alt="DevFest Indore" class="logo-image" />
        </router-link>
        <span class="location-tag">Indore</span>
      </div>
      <div class="mobile-overlay" :class="{ 'active': isMobileMenuOpen }" @click="closeMobileMenu"></div>
      <div class="right-section" :class="{ 'mobile-open': isMobileMenuOpen }">
        <ul class="nav-links">
          <li>
            <router-link to="/" class="nav-link" active-class="active" @click="closeMobileMenu">Home</router-link>
          </li>
          <li>
            <router-link to="/agenda" class="nav-link" active-class="active" @click="closeMobileMenu">Agenda</router-link>
          </li>
          <li>
            <router-link to="/speakers" class="nav-link" active-class="active" @click="closeMobileMenu">Speakers</router-link>
          </li>
          <li>
            <router-link to="/badge" class="nav-link" active-class="active" @click="closeMobileMenu">Badge</router-link>
          </li>
          <li>
            <router-link to="/sponsors" class="nav-link" active-class="active" @click="closeMobileMenu">Sponsors</router-link>
          </li>
          <li>
            <router-link to="/team" class="nav-link" active-class="active" @click="closeMobileMenu">Team</router-link>
          </li>
          <li>
            <router-link to="/faq" class="nav-link" active-class="active" @click="closeMobileMenu">FAQ</router-link>
          </li>
        </ul>
        <button class="register-btn" @click="handleRegister">Register Now</button>
      </div>
      <button class="mobile-menu-toggle" @click="toggleMobileMenu" aria-label="Toggle menu">
        <span class="hamburger-line" :class="{ 'active': isMobileMenuOpen }"></span>
        <span class="hamburger-line" :class="{ 'active': isMobileMenuOpen }"></span>
        <span class="hamburger-line" :class="{ 'active': isMobileMenuOpen }"></span>
      </button>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'HeaderComponent',
  data() {
    return {
      isMobileMenuOpen: false
    }
  },
  methods: {
    handleRegister() {
      window.open('https://konfhub.com/pre-devfest-indore', '_blank')
    },
    toggleMobileMenu() {
      this.isMobileMenuOpen = !this.isMobileMenuOpen
    },
    closeMobileMenu() {
      this.isMobileMenuOpen = false
    }
  }
}
</script>

<style scoped>
.header {
  background-color: #ffffff;
  padding: 0.75rem 2rem;
  display: flex;
  justify-content: center;
  position: sticky;
  top: 0;
  z-index: 1000;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
}

.nav {
  width: 80%;
  background-color: #F0F0F0;
  border-radius: 50px;
  padding: 0.5rem 1.5rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
  overflow: hidden;
}

.logo-section {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  flex-shrink: 0;
}

.right-section {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  flex-shrink: 0;
}

.logo-icon {
  display: flex;
  align-items: center;
}

.logo-icon svg {
  width: 24px;
  height: 24px;
}

.logo-link {
  display: flex;
  align-items: center;
  text-decoration: none;
  transition: opacity 0.2s;
}

.logo-link:hover {
  opacity: 0.8;
}

.logo-image {
  height: 32px;
  width: auto;
  object-fit: contain;
  display: block;
}

.location-tag {
  background-color: #ffffff;
  color: #333333;
  padding: 0.2rem 0.6rem;
  border-radius: 50px;
  border: 1px solid #000000;
  font-size: 0.75rem;
  font-weight: normal;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  white-space: nowrap;
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 0.75rem;
  margin: 0;
  padding: 0;
  align-items: center;
  flex-wrap: wrap;
}

.nav-link {
  color: #333333;
  text-decoration: none;
  padding: 0.4rem 0.875rem;
  font-size: 0.875rem;
  font-weight: normal;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  border-radius: 50px;
  transition: background-color 0.2s;
  white-space: nowrap;
}

.nav-link:hover {
  background-color: rgba(0, 0, 0, 0.05);
}

.nav-link.active {
  background-color: #D0D0D0;
  color: #333333;
}

.register-btn {
  background-color: #FBBC04;
  color: #333333;
  border: 1px solid #000000;
  padding: 0.5rem 1.25rem;
  border-radius: 50px;
  font-size: 0.875rem;
  font-weight: bold;
  cursor: pointer;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  transition: all 0.2s;
  white-space: nowrap;
}

.register-btn:hover {
  background-color: #F9AB00;
  transform: translateY(-1px);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.mobile-menu-toggle {
  display: none;
  flex-direction: column;
  gap: 4px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0.5rem;
  z-index: 1001;
}

.hamburger-line {
  width: 24px;
  height: 2px;
  background-color: #333333;
  border-radius: 2px;
  transition: all 0.3s ease;
}

.hamburger-line.active:nth-child(1) {
  transform: rotate(45deg) translate(6px, 6px);
}

.hamburger-line.active:nth-child(2) {
  opacity: 0;
}

.hamburger-line.active:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
}

.mobile-overlay {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 999;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.mobile-overlay.active {
  opacity: 1;
}

/* Responsive adjustments */
@media (max-width: 1024px) {
  .nav-links {
    gap: 0.5rem;
  }
  
  .nav-link {
    padding: 0.35rem 0.7rem;
    font-size: 0.8125rem;
  }
  
  .logo-image {
    height: 28px;
  }
  
  .right-section {
    gap: 0.5rem;
  }
  
  .register-btn {
    padding: 0.45rem 1rem;
    font-size: 0.8125rem;
  }
}

@media (max-width: 768px) {
  .header {
    padding: 0.5rem 1rem;
  }
  
  .nav {
    width: 100%;
    padding: 0.5rem 1rem;
    position: relative;
  }
  
  .mobile-menu-toggle {
    display: flex;
  }
  
  .mobile-overlay {
    display: block;
  }
  
  .right-section {
    position: fixed;
    top: 0;
    right: -100%;
    width: 280px;
    height: 100vh;
    background-color: #F0F0F0;
    flex-direction: column;
    align-items: flex-start;
    padding: 5rem 1.5rem 2rem;
    gap: 1.5rem;
    transition: right 0.3s ease;
    box-shadow: -2px 0 8px rgba(0, 0, 0, 0.1);
    overflow-y: auto;
    z-index: 1000;
  }
  
  .right-section.mobile-open {
    right: 0;
  }
  
  .nav-links {
    width: 100%;
    flex-direction: column;
    gap: 0.5rem;
    align-items: flex-start;
  }
  
  .nav-link {
    width: 100%;
    padding: 0.75rem 1rem;
    font-size: 0.875rem;
    display: block;
  }
  
  .register-btn {
    width: 100%;
    padding: 0.75rem 1.25rem;
    font-size: 0.875rem;
  }
  
  .logo-image {
    height: 28px;
  }
  
  .location-tag {
    font-size: 0.7rem;
    padding: 0.15rem 0.5rem;
  }
}

@media (max-width: 480px) {
  .header {
    padding: 0.5rem 0.75rem;
  }
  
  .nav {
    padding: 0.5rem 0.75rem;
  }
  
  .logo-image {
    height: 24px;
  }
  
  .location-tag {
    font-size: 0.65rem;
    padding: 0.1rem 0.4rem;
  }
  
  .right-section {
    width: 100%;
    right: -100%;
  }
  
  .right-section.mobile-open {
    right: 0;
  }
}
</style>