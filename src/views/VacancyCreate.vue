<template>
  <v-container fluid fill-height>
    <v-layout row wrap justify-center>
      <v-flex xs12 sm10 md8>
        <v-card elevation="5">
          <v-toolbar-title flat card>
            <h2 class="text-xs-center headline my-3">Create vacancy</h2>
          </v-toolbar-title>
          <v-stepper v-model="e1" vertical>
            <v-stepper-step :complete="e1 > 1" step="1">Name of step 1</v-stepper-step>
            <v-stepper-step :complete="e1 > 2" step="2">Name of step 2</v-stepper-step>
            <v-stepper-step :complete="e1 > 3" step="3">Name of step 3</v-stepper-step>
            <v-stepper-step :complete="e1 > 4" step="4">Name of step 4</v-stepper-step>
            <v-stepper-step :complete="e1 > 5" step="5">Name of step 5</v-stepper-step>
            <v-stepper-step :complete="e1 > 6" step="6">Name of step 6</v-stepper-step>
            <v-stepper-step :complete="e1 > 7" step="7">Name of step 7</v-stepper-step>
            <v-stepper-items>
              <v-stepper-content step="1">
                <FirstStepper />
                <v-layout justify-end>
                  <v-btn color="yellow darken-2" @click="e1 = 2">Далее</v-btn>
                </v-layout>
              </v-stepper-content>
              <v-stepper-content step="2">
                <SecondStepper />
                <v-layout justify-between class="mt-3">
                  <v-btn color="yellow darken-2" @click="e1 = 1">Назад</v-btn>
                  <v-spacer></v-spacer>
                  <v-btn color="yellow darken-2" @click="e1 = 3">Далее</v-btn>
                </v-layout>
              </v-stepper-content>
              <v-stepper-content step="3">
                <ThirdStepper />
                <v-layout justify-between class="mt-3">
                  <v-btn color="yellow darken-2" @click="e1 = 2">Назад</v-btn>
                  <v-spacer></v-spacer>
                  <v-btn color="yellow darken-2" @click="e1 = 4">Далее</v-btn>
                </v-layout>
              </v-stepper-content>
              <v-stepper-content step="4">
                <FourthStepper />
                <v-layout justify-between class="mt-3">
                  <v-btn color="yellow darken-2" @click="e1 = 3">Назад</v-btn>
                  <v-spacer></v-spacer>
                  <v-btn color="yellow darken-2" @click="e1 = 5">Далее</v-btn>
                </v-layout>
              </v-stepper-content>
              <v-stepper-content step="5">
                <FifthStepper />
                <v-layout justify-between class="mt-3">
                  <v-btn color="yellow darken-2" @click="e1 = 4">Назад</v-btn>
                  <v-spacer></v-spacer>
                  <v-btn color="yellow darken-2" @click="e1 = 6">Далее</v-btn>
                </v-layout>
              </v-stepper-content>
              <v-stepper-content step="6">
                <SixthStepper />
                <v-layout justify-between class="mt-3">
                  <v-btn color="yellow darken-2" @click="e1 = 5">Назад</v-btn>
                  <v-spacer></v-spacer>
                  <v-btn color="yellow darken-2" @click="e1 = 7">Далее</v-btn>
                </v-layout>
              </v-stepper-content>
              <v-stepper-content step="7">
                <SeventhStepper />
                <v-layout justify-between class="mt-3">
                  <v-btn color="yellow darken-2" @click="e1 = 6">Назад</v-btn>
                  <v-spacer></v-spacer>
                  <v-btn color="yellow darken-2" @click="onSubmit">Опубликовать</v-btn>
                </v-layout>
              </v-stepper-content>
            </v-stepper-items>
          </v-stepper>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
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
  },
  data () {
    return {
      e1: 0
    }
  },
  methods: {
    onSubmit () {
      console.log('On Submit')
    }
  }
}
</script>
