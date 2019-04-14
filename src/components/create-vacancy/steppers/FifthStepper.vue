<template>
  <v-layout row wrap>
    <v-flex xs6>
      <h3>Профессии</h3>
      <v-list>
        <template v-for="(language, index) in languages">
          <v-list-group no-action sub-group :key="language.id" v-if='language.level_of_proficiency'>
            <v-list-tile slot="activator" class="v-list__no_hover">
              <v-checkbox :label="language.name" v-model="language.value">
              </v-checkbox>
            </v-list-tile>
            <v-radio-group style="margin-left:80px!important" v-model="language.level_of_proficiency_code">
              <template v-for="level in language.level_of_proficiency">
                <v-radio :label="level.name" :value="level.id" :key='level.id'>
                </v-radio>
              </template>
            </v-radio-group>
          </v-list-group>
          <v-list-group no-action sub-group :key="language.id" v-else
            @click.once="getLevelLanguage(language.id,index)">
            <v-list-tile slot="activator" class="v-list__no_hover">
              <v-checkbox :label="language.name" v-model="language.value">
              </v-checkbox>
            </v-list-tile>
            <v-radio-group style="margin-left:80px!important" v-model="language.level_of_proficiency_code">
              <template v-for="level in language.level_of_proficiency">
                <v-radio :label="level.name" :value="level.id" :key='level.id'>
                </v-radio>
              </template>
            </v-radio-group>
          </v-list-group>
        </template>
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
