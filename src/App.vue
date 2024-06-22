<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated style="background-color: rgba(128, 128, 128, 0.5);">
      <q-toolbar>
        <q-btn-group flat>
          <q-btn flat :to="{ name: 'Widget' }">Widget</q-btn>
          <q-btn flat :to="{ name: 'Tugas2' }">Tugas 2</q-btn>
          <q-btn flat :to="{ name: 'Tugas3' }">Tugas 3</q-btn>
          <q-btn flat :to="{ name: 'Tugas4' }">Tugas 4</q-btn>
          <q-btn flat :to="{ name: 'Tugas5' }">Tugas 5</q-btn>
          <q-btn flat :to="{ name: 'Tugas6' }">Tugas 6</q-btn>
        </q-btn-group>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue';
</script>

<style>
</style>
