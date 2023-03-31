<template>
  <footer class="bg-secondary d-flex flex-column align-center py-6">

    <div class="footer-menu">
      <v-btn variant="plain" size="large" :to="{ name: 'Menu' }">Menu</v-btn>
      <v-btn variant="plain" size="large" :to="{ name: 'Contact' }">Contact</v-btn>
      <v-btn variant="plain" size="large" :to="{ name: 'CGV' }">CGV</v-btn>
      <v-btn variant="plain" size="large" :to="{ name: 'Mentions légales' }">Mentions légales</v-btn>
    </div>
      <v-btn variant="plain" size="large" href="https://www.instagram.com/pausenatty/"><v-icon icon="mdi-instagram"></v-icon></v-btn>
  </footer>
</template>

<script>
export default {

}
</script>

<style>
.footer-menu{
  border-bottom: 1px solid #a8ddd9;
}
</style>