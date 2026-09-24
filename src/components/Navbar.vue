<template>
  <v-app-bar
    fixed
    flat
    height="80"
    :class="['kermene-navbar', { 'scrolled': isScrolled }]"
  >
    <v-container class="d-flex align-center justify-space-between py-0 px-4 max-width-xl">
      
      <!-- LOGO BRANDING KERMENÉ -->
      <div class="d-flex align-center cursor-pointer">
        <div class="logo-symbol mr-3">
          <span class="logo-inner"></span>
        </div>
        <span class="logo-text text-h6 font-weight-black white--text letter-spacing-tight">
          KERMENÉ<span class="primary--text">.</span>
        </span>
      </div>

      <!-- LIENS NAVIGATION CATALOGUE DE SERVICES -->
      <div class="d-none d-md-flex align-center nav-links-container">
        <a href="#services" class="nav-link text-body-2 font-weight-medium">Catalogue Services</a>
        <a href="#applications" class="nav-link text-body-2 font-weight-medium">Applications</a>
        <a href="#infrastructure" class="nav-link text-body-2 font-weight-medium">Infrastructures</a>
        <a href="#support" class="nav-link text-body-2 font-weight-medium">Support & Demandes</a>
      </div>

      <!-- ACTIONS -->
      <div class="d-flex align-center nav-actions">
        <v-btn
          text
          dark
          class="text-none font-weight-semibold text-caption d-none d-sm-flex rounded-lg px-4"
          height="40"
        >
          Espace Intranet
        </v-btn>

        <v-btn
          color="primary"
          elevation="0"
          class="text-none font-weight-bold text-caption rounded-lg px-5 request-btn"
          height="40"
        >
          Nouvelle Demande
          <v-icon right x-small class="ml-1">mdi-plus</v-icon>
        </v-btn>
      </div>

    </v-container>
  </v-app-bar>
</template>

<script>
export default {
  name: 'Navbar',

  data() {
    return {
      isScrolled: false
    }
  },

  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },

  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll)
  },

  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY > 30
    }
  }
}
</script>

<style scoped>
.max-width-xl {
  max-width: 1280px;
}

.nav-links-container {
  gap: 32px;
}

.nav-actions {
  gap: 12px;
}

/* NAVBAR DE BASE */
.kermene-navbar {
  background: transparent !important;
  border-bottom: 1px solid rgba(255, 255, 255, 0.03) !important;
  transition: all 0.35s cubic-bezier(0.16, 1, 0.3, 1) !important;
}

/* ÉTAT SCROLLÉ */
.kermene-navbar.scrolled {
  background: rgba(7, 8, 12, 0.85) !important;
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.08) !important;
  box-shadow: 0 10px 30px -10px rgba(0, 0, 0, 0.5) !important;
}

/* BRANDING LOGO */
.logo-symbol {
  width: 28px;
  height: 28px;
  border-radius: 8px;
  background: linear-gradient(135deg, #2563eb 0%, #0284c7 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2px;
}

.logo-inner {
  width: 100%;
  height: 100%;
  background-color: #07080c;
  border-radius: 6px;
}

.letter-spacing-tight {
  letter-spacing: -0.04em;
}

/* LIENS DE NAVIGATION */
.nav-link {
  color: #9ca3af;
  text-decoration: none;
  transition: color 0.2s ease;
}

.nav-link:hover {
  color: #ffffff;
}

/* BOUTON ACTION */
.request-btn {
  background: linear-gradient(135deg, #2563eb 0%, #1d4ed8 100%) !important;
  box-shadow: 0 0 20px rgba(37, 99, 235, 0.35);
  transition: all 0.3s ease !important;
}

.request-btn:hover {
  box-shadow: 0 0 28px rgba(37, 99, 235, 0.55);
  transform: translateY(-1px);
}
</style>
