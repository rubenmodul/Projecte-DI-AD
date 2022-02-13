<template>
  <q-layout view="hHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title> Qualificacions App </q-toolbar-title>

        <div>{{ fecha }}</div>
      </q-toolbar>
    </q-header>
    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<style lang="scss" scoped>
.login {
  padding: 2rem;
}
.title {
  text-align: center;
}
.form {
  margin: 3rem auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 20%;
  min-width: 350px;
  max-width: 100%;
  background: rgba(246, 247, 248, 0.9);
  border-radius: 5px;
  padding: 40px;
  box-shadow: 0 4px 10px 4px rgba(0, 0, 0, 0.3);
}
.form-label {
  margin-top: 2rem;
  color: black;
  margin-bottom: 0.5rem;
  &:first-of-type {
    margin-top: 0rem;
  }
}
.form-input {
  padding: 10px 15px;
  background: none;
  background-image: none;
  border: 1px solid black;
  color: gray;
  &:focus {
    outline: 0;
    border-color: #1ab188;
  }
}
.form-submit {
  background: #1ab188;
  border: none;
  color: white;
  margin-top: 3rem;
  padding: 1rem 0;
  cursor: pointer;
  &:hover {
    background: #0b9185;
  }
}
</style>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Login',
    caption: 'login',
    icon: 'login',
    link: 'http://localhost:8080/#/'
  },
  {
    title: 'About',
    caption: 'About me',
    icon: 'person',
    link: 'http://localhost:8080/#/about'
  }
]

import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  },
  computed: {
    fecha () {
      const meses = [
        'Gener',
        'Febrer',
        'Març',
        'Abril',
        'Maig',
        'Juny',
        'Juliol',
        'Agost',
        'Septembre',
        'Octubre',
        'Novembre',
        'Desembre'
      ]
      const hoy = new Date()
      const diaSemana = hoy.toLocaleDateString('ca-CA', { weekday: 'long' })
      const diaSemanaMayus =
        diaSemana.charAt(0).toUpperCase() + diaSemana.slice(1)
      return (
        diaSemanaMayus +
        ', ' +
        hoy.getDate() +
        ' de ' +
        meses[hoy.getMonth()] +
        ' de ' +
        hoy.getFullYear()
      )
    }
  }
})
</script>
