<template>
  <v-form ref="form">
    <v-layout class="mb-4" column>
      <v-select class="no-text-details mb-4" :items="filter_items_country" v-model="filterCountry"
        label="Выберите страну" clearable></v-select>
      <v-select class="no-text-details mb-4" :items="filter_items_region" v-model="filterRegion"
        label="Выберите область" clearable></v-select>
      <v-select class="no-text-details" :items="filter_items_city" v-model="filter_city" label="Выберите город"
        clearable></v-select>
    </v-layout>
    <v-btn class="mb-4" @click="chooseGeograpy()">Добавить</v-btn>
    <v-layout row>
      <v-badge v-for="geogr in choosen_geography" :key="geogr.id" class="mr-2" overlap>
        <v-icon class="cursor-pointer" slot="badge" small @click="deleteChoosenGeography(geogr.id)">clear</v-icon>
        <v-btn>{{geogr.country}} {{geogr.region}} {{geogr.city}}</v-btn>
      </v-badge>
    </v-layout>
  </v-form>
</template>
<script>
export default {
  methods: {
    chooseGeograpy () {
    }
  }
}
</script>
