<template lang="pug">
  //-
    <!--<v-container fluid fill-height>
    <v-layout row justify-center>
      <v-flex xs12 sm10>
        <v-card elevation="5">
          <v-toolbar-title flat card>
            <h2 class="text-xs-center headline my-3">Create vacancy</h2>
          </v-toolbar-title>
          <v-stepper v-model="e1" vertical>
            <v-stepper-step :complete="e1 > 1" step="1">
              Основная информация
              <v-stepper-content step="1">
                <FirstStepper />
                <v-layout justify-end>
                  <v-btn color="yellow darken-2" @click="e1 = 2">Далее</v-btn>
                </v-layout>
              </v-stepper-content>
            </v-stepper-step>
            <v-stepper-step :complete="e1 > 2" step="2">
              Формат работы и занятость
              <v-stepper-content step="2">
                <SecondStepper />
                <v-layout justify-between class="mt-3">
                  <v-btn color="yellow darken-2" @click="e1 = 1">Назад</v-btn>
                  <v-spacer></v-spacer>
                  <v-btn color="yellow darken-2" @click="e1 = 3">Далее</v-btn>
                </v-layout>
              </v-stepper-content>
            </v-stepper-step>
            <v-stepper-step :complete="e1 > 3" step="3">
              Профессии и сферы деятельности
              <v-stepper-content step="3">
                <ThirdStepper />
                <v-layout justify-between class="mt-3">
                  <v-btn color="yellow darken-2" @click="e1 = 2">Назад</v-btn>
                  <v-spacer></v-spacer>
                  <v-btn color="yellow darken-2" @click="e1 = 4">Далее</v-btn>
                </v-layout>
              </v-stepper-content>
            </v-stepper-step>
            <v-stepper-step :complete="e1 > 4" step="4">
              Категории прав и автомобили
              <v-stepper-content step="4">
                <FourthStepper />
                <v-layout justify-between class="mt-3">
                  <v-btn color="yellow darken-2" @click="e1 = 3">Назад</v-btn>
                  <v-spacer></v-spacer>
                  <v-btn color="yellow darken-2" @click="e1 = 5">Далее</v-btn>
                </v-layout>
              </v-stepper-content>
            </v-stepper-step>
            <v-stepper-step :complete="e1 > 5" step="5">
              Язык
              <v-stepper-content step="5">
                <FifthStepper />
                <v-layout justify-between class="mt-3">
                  <v-btn color="yellow darken-2" @click="e1 = 4">Назад</v-btn>
                  <v-spacer></v-spacer>
                  <v-btn color="yellow darken-2" @click="e1 = 6">Далее</v-btn>
                </v-layout>
              </v-stepper-content>
            </v-stepper-step>
            <v-stepper-step :complete="e1 > 6" step="6">
              Зароботная плата
              <v-stepper-content step="6">
                <SixthStepper />
                <v-layout justify-between class="mt-3">
                  <v-btn color="yellow darken-2" @click="e1 = 5">Назад</v-btn>
                  <v-spacer></v-spacer>
                  <v-btn color="yellow darken-2" @click="e1 = 7">Далее</v-btn>
                </v-layout>
              </v-stepper-content>
            </v-stepper-step>
            <v-stepper-step :complete="e1 > 7" step="7">
              География размещения
              <v-stepper-content step="7">
                <SeventhStepper />
                <v-layout justify-between class="mt-3">
                  <v-btn color="yellow darken-2" @click="e1 = 6">Назад</v-btn>
                  <v-spacer></v-spacer>
                  <v-btn color="yellow darken-2" @click="onSubmit">Опубликовать</v-btn>
                </v-layout>
              </v-stepper-content>
            </v-stepper-step>
          </v-stepper>
        </v-card>
      </v-flex>
    </v-layout>
    </v-container> -->
  v-content
    v-container(fluid fill-height)
      v-layout(justify-center)
        v-flex
          v-stepper(v-model="currentStep" vertical)
            v-stepper-step(:class="{'active-step': !isCreated}" step="1" :complete="currentStep > 1" editable)
              | Основная информация
            v-stepper-content(step="1")
              first-stepper(@getValidFirstStep="getValidFirstStep" :validate="validate" :info.sync="info")
              v-layout(justify-end)
                v-btn(color="primary" @click="isCreated ? currentStep = 2 : currentStep = 3") Далее
            v-stepper-step(step="2" :complete="isCreated ? currentStep > 2 : false" :editable="isCreated")
              | Формат работы и занятость
            v-stepper-content(step="2")
              second-stepper(@getContractors="getContractors" @getDefaultContractors="getDefaultContractors" :createdContractors="createdContractors" :isCreated="isCreated" :fromServer="contractorsFromServer" :items="contractors")
              v-layout(justify-space-between)
                v-btn(@click="currentStep = 1" color="primary") Назад
                v-btn(@click="currentStep = 3" color="primary") Далее
            v-stepper-step(:class="{'active-step': !isCreated}" step="3" :complete="currentStep > 3" editable)
              | Профессии и сферы деятельности
            v-stepper-content(step="3")
              third-stepper(@getValidSecondStep="getValidSecondStep" :items="fieldOfActivityList" :fromServer="fieldOfActivityFromServer")
              v-layout(justify-space-between)
                v-btn(@click="isCreated ? currentStep = 2 : currentStep = 1" color="primary") Назад
                v-btn(@click="isCreated ? currentStep = 4 : currentStep = 6" color="primary") Далее
            v-stepper-step(step="4" :complete="isCreated ? currentStep > 4 : false" :editable="isCreated")
              | Категории прав и автомобили
            v-stepper-content(step="4")
              fourth-stepper(@getEmployees="getEmployees" @getToLayOffEmployees="getToLayOffEmployees" :fromServer="employeesFromServer" :isCreated="isCreated" :createdChangedEmployees="createdChangedEmployees")
              v-layout(justify-space-between)
                v-btn(@click="currentStep = 3" color="primary") Назад
                v-btn(@click="currentStep = 5" color="primary") Далее
            v-stepper-step(step="5" :complete="isCreated ? currentStep > 5 : false" :editable="isCreated")
              | Языки
            v-stepper-content(step="5")
              fifth-stepper
              v-layout(justify-space-between)
                v-btn(@click="currentStep = 4" color="primary") Назад
                v-btn(@click="currentStep = 6" color="primary") Далее
            v-stepper-step(:class="{'active-step': !isCreated}" step="6" :fromServer="fieldOfActivityList" :complete="currentStep > 6" editable)
              | Заработная плата
            v-stepper-content(step="6")
              sixth-stepper(@getValidThirdStep="getValidThirdStep" :fromServer="geographyFromServer" :countryList="countryList" )
              v-layout(justify-space-between)
                v-btn(@click="isCreated ? currentStep = 5 : currentStep = 3" color="primary") Назад
                v-btn(@click="isCreated ? currentStep = 7 : currentStep = 1" color="primary") Далее
            v-stepper-step(step="7" :complete="isCreated ? currentStep > 7 : false" :editable="isCreated")
              | География ремещения
          v-layout(justify-end)
            v-btn(@click="isCreated? changeCompany() : createCompany()" color="primary") Архивировать
            v-btn(@click="isCreated? changeCompany() : createCompany()" color="primary") Опубликовать
            v-btn(@click="isCreated? changeCompany() : createCompany()" color="primary") Удалить
</template>

<script>
import FirstStepper from '@/components/create-vacancy/steppers/FirstStepper.vue'
import SecondStepper from '@/components/create-vacancy/steppers/SecondStepper.vue'
import ThirdStepper from '@/components/create-vacancy/steppers/ThirdStepper.vue'
import FourthStepper from '@/components/create-vacancy/steppers/FourthStepper.vue'
import FifthStepper from '@/components/create-vacancy/steppers/FifthStepper.vue'
import SixthStepper from '@/components/create-vacancy/steppers/SixthStepper.vue'
import SeventhStepper from '@/components/create-vacancy/steppers/SeventhStepper.vue'
export default {
  components: {
    FirstStepper, SecondStepper, ThirdStepper, FourthStepper, FifthStepper, SixthStepper, SeventhStepper
  }
}
</script>

<style>
  .v-tabs__div {
    width: 50%;
  }
</style>
