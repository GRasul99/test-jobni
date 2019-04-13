<template>
  <v-app>
    <v-navigation-drawer
      app
      temporary
      v-model="drawer"
    >
    </v-navigation-drawer>
    <v-toolbar app color="yellow darken-2">
      <v-toolbar-side-icon
        @click="drawer = !drawer"
      >
      </v-toolbar-side-icon>
    </v-toolbar>

    <v-content>
      <router-view/>
    </v-content>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  data () {
    return {
      drawer: false
    }
  }
}
</script>
