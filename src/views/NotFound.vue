<template>
  <q-layout view="lhh LpR lff">
    <q-page-container>
      <q-page class="page-404">
        <!-- Texto -->
        <h1 class="code">404</h1>
        <h2 class="title">Pagina no encontrada</h2>
        <p class="subtitle">
          Parece que la página que buscas no existe o ha sido movida.
        </p>

        <!-- Botones -->
        <div class="actions">
          <q-btn
            label="Regresar"
            color="green-6"
            outline
            rounded
            icon="arrow_back"
            @click="goBack"
            class="q-mr-sm"
          />
          <q-btn
            label="Inicio"
            color="green-6"
            unelevated
            rounded
            icon="home"
            @click="goHome"
          />
        </div>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { useRouter } from 'vue-router'

const router = useRouter()

const goBack = () => router.back()
const goHome = () => router.push('/')
</script>

<style scoped>
.page-404 {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  background: #ffffff;
  padding: 2rem;
  text-align: center;
  font-family: 'Inter', sans-serif;
}

/* Ilustración */
.illustration {
  width: 160px;
  height: 160px;
  margin: 0 0 1.5rem;
}
.illustration svg {
  width: 100%;
  height: 100%;
  animation: float 4s ease-in-out infinite;
}
@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-8px); }
}

/* Tipografía */
.code {
  font-size: 6rem;
  font-weight: 800;
  color: #e0e0e0;
  letter-spacing: -0.05em;
  margin: 0 0 0.25rem;
}
.title {
  font-size: 1.5rem;
  font-weight: 600;
  color: #388e3c;
  margin: 0 0 0.5rem;
}
.subtitle {
  font-size: 1rem;
  color: #9e9e9e;
  margin: 0 0 2rem;
  max-width: 320px;
}

/* Botones */
.actions {
  display: flex;
  gap: 0.75rem;
}
.actions .q-btn {
  text-transform: none;
  font-weight: 500;
  letter-spacing: 0.3px;
  padding: 0.5rem 1.5rem;
}

/* Responsive */
@media (max-width: 480px) {
  .code { font-size: 4rem; }
  .title { font-size: 1.25rem; }
  .actions { flex-direction: column; width: 100%; }
  .actions .q-btn { width: 100%; }
}
</style>