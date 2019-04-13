<template>
  <v-layout row wrap>
    <v-flex xs6>
      <h3>Профессии</h3>
      <v-list>
        <v-list-group
          v-for="chekboxLabel in chekboxLabels"
          :key="chekboxLabel.title"
          no-action
        >
          <template v-slot:activator>
            <v-list-tile>
              <v-checkbox
                v-model="checkbox"
                :label="chekboxLabel.title"
              ></v-checkbox>
            </v-list-tile>
          </template>
          <!--<v-list-tile
            v-for="(subChekboxLabel,index) in subChekboxLabel.subChekboxLabels"
            :key="index"
          >
            <v-list-tile-content>
              <v-list-tile-title>{{ subChekboxLabel.title }}</v-list-tile-title>
            </v-list-tile-content>

            <v-list-tile-action>
              <v-icon>{{ subChekboxLabel.action }}</v-icon>
            </v-list-tile-action>
          </v-list-tile> -->
        </v-list-group>
      </v-list>
    </v-flex>
    <v-flex xs6>
      <h3>Сферы деятельности</h3>
      <v-list>
        <v-list-tile
          v-for="(secondCheckbox,index) in secondChekboxLabels"
          :key="index"
        >
          <v-checkbox
            v-model="secondCheckboxч"
            :label="secondCheckbox.title"
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
      value: '',
      checkbox: '',
      chekboxLabels: [
        {
          action: 'restaurant',
          title: 'Програмисст',
          active: false,
          subChekboxLabels: [
            { title: 'PHP' },
            { title: 'Pyhton' },
            { title: 'Delphi' },
            { title: 'Django' }
          ]
        }
      ],
      secondChekboxLabels: [
        { title: 'Логистика' },
        { title: 'Медицина' },
        { title: 'Металлургия' },
        { title: 'Нефтиняая промышленность' },
        { title: 'Продажи' },
        { title: 'Туризм и отдых' }
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
