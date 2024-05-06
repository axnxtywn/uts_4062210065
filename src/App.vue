<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import Experiment from './components/Experiment.vue'
import MhsForm from '@/components/MahasiswaForm.vue'
import LethNav from '@/components/navbar/LethNav.vue'
</script>

<template>
  <v-layout class="rounded rounded-md">
    <v-app-bar color="primary" title="Aplikasi Penjadwalan Kuliah"></v-app-bar>

    <LethNav> </LethNav>

    <v-main class="d-flex align-center justify-center" style="min-height: 300px">
      <RouterView> </RouterView>
    </v-main>
  </v-layout>
</template>
