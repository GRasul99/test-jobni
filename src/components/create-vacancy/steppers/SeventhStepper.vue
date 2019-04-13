<template>
  <v-form ref="form">
    <v-layout class="mb-4" column>
      <v-select label="Выберите страну" clearable></v-select>
      <v-select label="Выберите область" clearable></v-select>
      <v-select label="Выберите город" clearable></v-select>
    </v-layout>
    <v-btn color="yellow darken-2" @click="onSubmit">Опубликовать</v-btn>

  </v-form>
</template>