<template>
  <q-page class="forNow">
    <q-card class="my-card">
      <q-card-section>
        <div class="text-h6">Weather Widget</div>
      </q-card-section>

      <q-card-section>
        <q-input
          v-model="location"
          label="Enter location"
          outlined
          :label-color="'white'"
          style="color: aliceblue;"
          input-class="input-white"
        />
        <q-btn @click="fetchWeather" label="Search" color="primary" class="q-mt-md" />
      </q-card-section>

      <q-card-section v-if="weather" class="weather-output">
        <div>{{ weather.name }}</div>
        <div>Temperature: {{ weather.main.temp }}°C</div>
        <div>Weather: {{ weather.weather[0].description }}</div>
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script setup>
import { ref } from 'vue';
import axios from 'axios';

const location = ref('');
const weather = ref(null);

const fetchWeather = async () => {
  const apiKey = '37321f81fafbb8b75103aa766c331043';
  try {
    const response = await axios.get(`https://api.openweathermap.org/data/2.5/weather?q=${location.value}&appid=${apiKey}&units=metric`);
    weather.value = response.data;
  } catch (error) {
    console.error(error);
  }
};
</script>

<style>
.my-card {
  max-width: 400px;
  margin: 0 auto;
  text-align: center;
  margin-top: 50px;
  background-color: transparent;
  backdrop-filter: blur(5px);
}

.text-h6 {
  font-weight: bold;
  color: aliceblue;
}

.input-white .q-field__native {
  color: aliceblue;
}

.weather-output {
  color: aliceblue;
}
</style>
