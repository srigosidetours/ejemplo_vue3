<template>
  <q-layout view="hHh lpR fFf">
    <q-header class="bg-primary text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg" />
          </q-avatar>
          Title
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <NuxtPage />
    </q-page-container>

    <q-footer class="bg-blue-4 text-white">
      <q-toolbar>
        <nuxt-link to="/about" exact-active-class="active">About</nuxt-link>
        <nuxt-link to="/" exact-active-class="active">Home</nuxt-link>
        <q-input dense v-model="mensajes.texto"></q-input>
        <AppAlert> {{ mensajes.texto }} </AppAlert>
      </q-toolbar>
      <q-toolbar>
        <ul>
          <li v-for="(item, index) in lista" :key="index">
            {{ item }}
          </li>
        </ul>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
export default {
  setup() {
    const lista = ref(["uno", "dos", "tres"]);
    const mensajes = ref({ texto: "coso", texto2: "coso2" });

    return {
      mensajes,
      lista,
    };
  },
};
</script>

<style>
.active {
  background-color: yellow;
  color: black;
}
</style>
