<template>
  <v-layout row wrap>
    <v-flex xs6>
      <h3>Катагории прав</h3>
      <v-radio-group v-model="radioGroup">
        <v-radio
          v-for="(radioLabel,index) in radioLabels"
          :key="index"
          :label="radioLabel.title"
          :value="radioLabel"
        ></v-radio>
      </v-radio-group>
    </v-flex>
    <v-flex xs6>
      <v-layout column>
        <v-select solo class="no-text-details pa-0 ma-0" :items="items_brand_car" v-model="brand" label="Марка">
        </v-select>
        <v-select solo class="no-text-details pa-0 ma-0" :items="items_fuel_car" v-model="fuel_type"
          label="Тип двигателя"></v-select>
        <v-select solo class="no-text-details pa-0 ma-0" :items="items_body_type" v-model="body_type"
          label="Тип кузова"></v-select>
        <v-text-field class="no-text-details" v-model="model" label="Модель"></v-text-field>
        <v-text-field type='number' class="no-text-details" v-model="year_of_manufacture" label="Год выпуска">
        </v-text-field>
        <v-text-field type="number" class="no-text-details" v-model="fuel_consumption_city"
          label="Расход топлива (город)"></v-text-field>
        <v-text-field type="number" class="no-text-details" v-model="fuel_consumption_highway"
          label="Расход топлива (трасса)"></v-text-field>
        <v-text-field type="number" class="no-text-details" v-model="cargo_capacity" label="Грузоподъемность">
        </v-text-field>
        <v-text-field type="number" class="no-text-details" v-model="capacity_liters"
          label="Емкость багажного отделения"></v-text-field>
        <v-text-field type="number" class="no-text-details" v-model="capacity_of_people" label="Вместимость">
        </v-text-field>
      </v-layout>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data () {
    return {
      radioGroup: '',
      checkbox: '',
      items_brand_car: '',
      items_fuel_car: '',
      items_body_type: '',
      brand: '',
      fuel_type: '',
      body_type: '',
      model: '',
      year_of_manufacture: '',
      fuel_consumption_city: '',
      fuel_consumption_highway: '',
      cargo_capacity: '',
      capacity_liters: '',
      capacity_of_people: '',
      radioLabels: [
        { title: 'A - мотоциклы' },
        { title: 'B - Легковые авто' },
        { title: 'C - Грузовые авто' },
        { title: 'D - Автобусы' },
        { title: 'E - Авто с прицепом' }
      ],
      items: []
    }
  }
}
</script>

<style>
.v-list {
  height: auto;
  max-height: 300px;
  overflow: auto;
}
</style>
