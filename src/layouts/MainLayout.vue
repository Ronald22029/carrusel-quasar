<template>
  <q-layout view="hHh lpR fFf">  <!-- Define la estructura del layout -->
    <!-- Encabezado -->
    <q-header elevated>
      <q-toolbar>
        <q-btn flat round icon="menu" @click="toggleLeftDrawer" />
        <q-toolbar-title>
          Mi Aplicación
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <!-- Barra lateral izquierda (drawer) -->
    <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered>
      <q-list>
        <q-item clickable v-ripple @click="goToPage('/')">
          <q-item-section avatar>
            <q-icon name="home" />
          </q-item-section>
          <q-item-section>
            Inicio
          </q-item-section>
        </q-item>

        <q-item clickable v-ripple @click="goToPage('/carousel')">
          <q-item-section avatar>
            <q-icon name="image" />
          </q-item-section>
          <q-item-section>
            Carrusel
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <!-- Contenedor de la página -->
    <q-page-container>
      <router-view /> <!-- Aquí se renderizan las páginas específicas -->
    </q-page-container>

    <!-- Pie de página -->
    <q-footer class="bg-primary text-white">
      <div class="text-center q-pa-md">
        © 2024 Mi Aplicación
      </div>
    </q-footer>
  </q-layout>
</template>

<script>
export default {
  data () {
    return {
      leftDrawerOpen: false
    }
  },
  methods: {
    toggleLeftDrawer () {
      this.leftDrawerOpen = !this.leftDrawerOpen
    },
    goToPage (page) {
      this.$router.push(page)
    }
  }
}
</script>

<style scoped>
/* Estilos personalizados */
</style>
