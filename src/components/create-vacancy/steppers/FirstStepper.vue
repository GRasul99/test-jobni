<template>
  <v-form ref="form" v-model="valid">
    <v-layout column>
      <v-text-field
        class="my-2"
        outline
        name="name"
        label="Наименование"
        id="id"
        v-model="vacancyName"
      ></v-text-field>
      <v-textarea
        outline
        name="name"
        label="Описание"
        id="id"
        v-model="description"
      ></v-textarea>
      <v-textarea
        outline
        name="name"
        label="Требование"
        id="id"
        v-model="requirenmets"
      ></v-textarea>
      <v-textarea
        outline
        name="name"
        label="Обязанности"
        id="id"
        v-model="duty"
      ></v-textarea>
    </v-layout>
  </v-form>
</template>

<script>
export default {
  data () {
    return {
      valid: false,
      vacancyName: '',
      description: '',
      requirenmets: '',
      duty: ''
    }
  }
}
</script>
