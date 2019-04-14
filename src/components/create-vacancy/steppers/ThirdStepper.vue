<template>
  <v-layout row wrap>
    <v-flex xs6>
      <h3>Профессии</h3>
        <v-list class="mt-2 professionsList">
          <template v-for="(profession, index) in professions">
            <v-list-group v-if="profession.competences" no-action sub-group :key="profession.id">
              <v-list-tile slot="activator">
                <v-checkbox :label="profession.name" v-model="profession.value">
                </v-checkbox>
              </v-list-tile>
              <v-list-tile v-for="competence in profession.competences" :key="competence.id">
                <v-checkbox :label="competence.name" v-model="competence.value">
                </v-checkbox>
              </v-list-tile>
            </v-list-group>
            <v-list-group v-else no-action sub-group @click.once="getCompetence(profession.id, index)"
              :key="profession.id">
              <v-list-tile slot="activator">
                <v-checkbox :label="profession.name" v-model="profession.value">
                </v-checkbox>
              </v-list-tile>
              <v-list-tile v-for="competence in profession.competences" :key="competence.id">
                <v-checkbox :label="competence.name" v-model="competence.value">
                </v-checkbox>
              </v-list-tile>
            </v-list-group>
          </template>
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
