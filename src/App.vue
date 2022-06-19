<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import Profile from './components/Profile.vue'
</script>

<template>
<div class="background">
  <Profile :dados="{
      nome: 'Kelvis Santos',
      foto: 'https://avatars.githubusercontent.com/u/71862581?v=4',
      github: 'https://github.com/kelvis-santos/',
      linkedin: 'https://www.linkedin.com/in/kelvis-santos/',
      instagram: 'https://www.instagram.com/kelvis_santos/',
      twitter: 'https://twitter.com/kelvis_santos/',
      facebook: 'https://www.facebook.com/kelvis.santos.3',
      email: 'kelvishenrique04@gmail.com',
      telefone: '(11) 98888-8888',
      endereco: 'Rua dos bobos, 0',
      cidade: 'São Paulo',
      estado: 'SP',
      pais: 'Brasil',
      cep: '00000-000',
      skype: 'kelvis.santos',
      whatsapp: '(11) 98888-8888',
      site: 'https://kelvis.santos.dev',
    }"
    msg="Olá, eu sou o Kelvis Santos"
  />
</div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
html {
  background-color:rgb(8, 32, 50);
}
</style>
