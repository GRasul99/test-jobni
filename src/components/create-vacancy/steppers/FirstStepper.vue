<template>
  <v-form ref="form">
    <v-layout column>
      <v-layout row wrap>
        <v-layout column>
          <v-text-field
            name="Name"
            label="Наименование"
            id="id"
          ></v-text-field>
          <v-textarea
            name="name"
            label="Описание"
            id="id"
            v-model="description"
          ></v-textarea>
          <v-textarea
            name="name"
            label="Требование"
            id="id"
            v-model="requirenmets"
          ></v-textarea>
          <v-textarea
            name="name"
            label="Обязанности"
            id="id"
            v-model="duty"
          ></v-textarea>
        </v-layout>
      </v-layout>
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

<style scoped>
.form {
  display: block;
}
</style>
