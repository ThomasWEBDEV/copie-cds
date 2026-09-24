cat << 'EOF' > src/components/Login.vue
<template>
  <div class="login-page">
    <main class="main-layout">
      <header class="top-header">
        <h1 class="main-title">CATALOGUE DE SERVICES</h1>
      </header>

      <!-- ZONE CENTRALE FIXE -->
      <div class="hero-stage">
        
        <!-- SPHÈRE EN ARRIÈRE-PLAN -->
        <div class="sphere-wrapper">
          <div class="sphere-crop">
            <iframe
              src="https://my.spline.design/sphereofparticles-pf8kCKhl87m7WBKbVRBgrPob/"
              frameborder="0"
              class="spline-iframe"
            ></iframe>
          </div>
        </div>

        <!-- CARTE AU PREMIER PLAN -->
        <div class="card-container">
          <div class="login-card">
            <form @submit.prevent="handleLogin" class="login-form">
              <div class="input-group">
                <label for="email">Identifiant / Email</label>
                <div class="input-wrapper">
                  <span class="input-icon">👤</span>
                  <input
                    id="email"
                    v-model="email"
                    type="text"
                    placeholder="E-mail professionnel"
                  />
                </div>
              </div>

              <div class="input-group">
                <label for="password">Mot de passe</label>
                <div class="input-wrapper">
                  <span class="input-icon">🔒</span>
                  <input
                    id="password"
                    v-model="password"
                    type="password"
                    placeholder="Votre mot de passe"
                  />
                </div>
              </div>

              <button type="submit" class="submit-btn">
                Connexion
              </button>
            </form>
          </div>
        </div>
      </div>

      <footer class="bottom-footer">
        <p>Accédez à vos services</p>
      </footer>
    </main>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    handleLogin() {
      console.log('Connexion :', this.email)
    }
  }
}
</script>

<style scoped>
.login-page {
  width: 100vw;
  height: 100vh;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background: #ffffff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Plus Jakarta Sans', sans-serif;
}

.main-layout {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  padding: 20px 0;
  box-sizing: border-box;
}

.top-header {
  margin-top: 65px;
}

.main-title {
  font-size: 0.85rem;
  font-weight: 600;
  color: #334155;
  letter-spacing: 0.35em;
  text-transform: uppercase;
  margin: 0;
}

.hero-stage {
  position: relative;
  width: 100%;
  max-width: 900px;
  height: 500px;
  margin: 0 auto;
}

/* CARTE DÉCALÉE À GAUCHE DU CENTRE */
.card-container {
  position: absolute;
  left: 50%;
  top: 45%;
  transform: translate(-50%, -50%) translateX(-140px);
  width: 360px;
  z-index: 10;
}

.login-card {
  width: 100%;
  padding: 36px;
  background: rgba(255, 255, 255, 0.15); 
  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  border-radius: 16px;
  border: 1px solid rgba(0, 0, 0, 0.05);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
}

.login-form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.input-group label {
  display: block;
  font-size: 0.8rem;
  color: #334155;
  margin-bottom: 8px;
  font-weight: 600;
}

.input-wrapper {
  position: relative;
  display: flex;
  align-items: center;
}

.input-icon {
  position: absolute;
  left: 14px;
  font-size: 0.85rem;
  color: #64748b;
  pointer-events: none;
}

.input-wrapper input {
  width: 100%;
  padding: 12px 14px 12px 40px;
  background: rgba(255, 255, 255, 0.5);
  border: 1px solid rgba(226, 232, 240, 0.8);
  border-radius: 8px;
  font-size: 0.9rem;
  color: #0f172a !important;
  outline: none;
  transition: all 0.2s ease;
}

.input-wrapper input:focus {
  border-color: #c25e22;
  background: #ffffff;
  box-shadow: 0 0 0 3px rgba(194, 94, 34, 0.15);
}

.submit-btn {
  margin-top: 10px;
  width: 100%;
  padding: 14px;
  border: none;
  border-radius: 8px;
  background: #c25e22;
  color: #ffffff;
  font-size: 0.9rem;
  font-weight: 600;
  cursor: pointer;
  box-shadow: 0 4px 14px rgba(194, 94, 34, 0.3);
  transition: background 0.2s;
}

.submit-btn:hover {
  background: #a84f1a;
}

.sphere-wrapper {
  position: absolute;
  left: 60%;
  top: 30%;
  transform: translate(-50%, -50%) translateX(120px);
  width: 550px;
  height: 550px;
  z-index: 1;
  mix-blend-mode: multiply; /* suppr le fond blanc */
  pointer-events: none;
}

.sphere-crop {
  width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;
}

.spline-iframe {
  width: 100%;
  height: calc(100% + 140px);
  border: none;
  margin-bottom: -140px;
  pointer-events: auto;
}

.bottom-footer {
  margin-bottom: 30px;
}

.bottom-footer p {
  font-size: 0.75rem;
  color: #64748b;
  letter-spacing: 0.25em;
  text-transform: uppercase;
  margin: 0;
}
</style>