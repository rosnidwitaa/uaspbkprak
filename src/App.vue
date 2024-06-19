<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title >
          WEATHER
        </q-toolbar-title>
        <q-btn-dropdown flat class="custom-btn" label="TUGAS ROSNEEYY" >
          <q-list>
            <q-item clickable @click="navigateToLink('https://rosniprojectcvgacor.vercel.app/?authuser=0')">
              <q-item-section>
                TUGAS 1
              </q-item-section>
            </q-item>
            <q-item clickable @click="navigateToLink('https://tugas2-rosni.vercel.app/?authuser=0')">
              <q-item-section>
                TUGAS 2
              </q-item-section>
            </q-item>
            <q-item clickable @click="navigateToLink('https://tugas3rosneey.vercel.app/?authuser=0')">
              <q-item-section>
                TUGAS 3
              </q-item-section>
            </q-item>
            <q-item clickable @click="navigateToLink('https://tugas-4-rosni.vercel.app/?authuser=0')">
              <q-item-section>
                TUGAS 4
              </q-item-section>
            </q-item>
            <q-item clickable @click="navigateToLink('https://tugas5-rosneeyy.vercel.app/?authuser=0')">
              <q-item-section>
                TUGAS 5
              </q-item-section>
            </q-item>
            <q-item clickable @click="navigateToLink('https://tugas6-rosneey.vercel.app/?authuser=0')">
              <q-item-section>
                TUGAS 6
              </q-item-section>
            </q-item>
            <q-item clickable @click="navigateToLink('https://tugas7-rosneeyy.vercel.app/?authuser=0')">
              <q-item-section>
                TUGAS 7
              </q-item-section>
            </q-item>
          </q-list>
        </q-btn-dropdown>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <q-page>
        <q-card class="q-pa-md">
          <q-card-section>
            <div class="text-h6">Weather Widget</div>
          </q-card-section>

          <q-card-section>
            <WeatherWidget />
          </q-card-section>
        </q-card>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script>
import WeatherWidget from './components/WeatherWidget.vue'

export default {
  name: 'App',
  components: {
    WeatherWidget
  },
  methods: {
    navigateToLink(url) {
      window.location.href = url;
    }
  }
}
</script>

<style>
.custom-btn {
  background-color: rgb(25, 25, 75);
  color: white;
}
.custom-btn .q-btn__content {
  color: white;
}
.custom-toolbar {
  background-color: navy;
  color: white;
}
</style>
