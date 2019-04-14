<template>
  <v-app>
    <v-navigation-drawer
      app
      temporary
      v-model="drawer"
    >
      <v-list>
        <v-list-tile>
          <v-list-tile-content>
            <v-list-tile-title>
              <v-btn flat to="/">Главный</v-btn>
            </v-list-tile-title>
          </v-list-tile-content>
          <v-list-tile-content>
            <v-list-tile-title>
              <v-btn flat to="/vacancy-create">Создать вакансию</v-btn>
            </v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
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
