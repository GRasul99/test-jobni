<template>
  <v-layout row wrap>
    <v-flex xs6>
      <h3>Формат работы</h3>
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
      <h3>Занятость</h3>
      <v-list>
        <v-list-tile
          v-for="(chekboxLabel,index) in chekboxLabels"
          :key="index"
        >
          <v-checkbox
            v-model="checkbox"
            :label="chekboxLabel.title"
          ></v-checkbox>
        </v-list-tile>
      </v-list>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data () {
    return {
      radioGroup: '',
      checkbox: '',
      radioLabels: [
        { title: 'В офисе' },
        { title: 'Удаленно' },
        { title: 'Не имеет значение' }
      ],
      chekboxLabels: [
        { title: 'Польный день' },
        { title: 'Частичная занятось' },
        { title: 'Посменно' },
        { title: 'Работа в вечернее время' },
        { title: 'Работа в ночное время' },
        { title: 'Работа в выходные' },
        { title: 'Вахта' },
        { title: 'По заявкам' },
        { title: 'Свободный график' },
        { title: 'Контракт' }
      ]
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
