<template>
  <div class="weather-container">
    <div class="weather-box">
      <h2>Cuaca</h2>
      <div class="input-container">
        <q-input v-model="city" placeholder="Masukkan Lokasi" />
        <q-btn label="Cari" @click="fetchWeather" color="blue" />
      </div>
      <div v-if="loading" class="loading">Loading data...</div>
      <div v-if="weather">
        <div class="weather-info">
          <div class="text-h6">{{ city }}</div>
          <div class="text-subtitle2">{{ weather.main.temp }}°C</div>
          <div class="text-subtitle2">{{ weather.weather[0].description }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';
import axios from 'axios';

export default {
  name: 'WeatherWidget',
  setup() {
    const city = ref('Mekkah');
    const weather = ref(null);
    const loading = ref(true);

    const fetchWeather = async () => {
      loading.value = true;
      const apiKey = '5adef2a1de3fa125328a60e4f60520d9'; // Replace with your API key
      try {
        const response = await axios.get(
          `https://api.openweathermap.org/data/2.5/weather?q=${city.value}&units=metric&appid=${apiKey}`
        );
        weather.value = response.data;
      } catch (error) {
        console.error('Error fetching weather data:', error);
      } finally {
        loading.value = false;
      }
    };

    return { city, weather, loading, fetchWeather };
  },
};
</script>

<style scoped>
.weather-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 90vw;
  background: url("https://img.freepik.com/free-photo/closeup-shot-thermometer-beach-sand_181624-12367.jpg?w=1480") center/cover no-repeat;
  min-height: 100vh;
  min-width: 90vw;
}

.weather-box {
  background: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  max-width: 300px;
  width: 100%;
}

.weather-box h2 {
  margin-bottom: 20px;
}

.input-container {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}

.loading {
  margin-top: 20px;
}

.weather-info {
  margin-top: 20px;
}

.text-h6 {
  font-size: 1.25rem;
  font-weight: bold;
}

.text-subtitle2 {
  font-size: 1rem;
}
</style>
