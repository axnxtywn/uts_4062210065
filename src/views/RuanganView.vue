<template>
  <v-container>
    <v-row>
      <h1>Entry Data Ruangan</h1>
    </v-row>
    <v-row>
      <v-text-field label="Kode Ruangan" variant="outlined" v-model="ruangan.kode"></v-text-field>
    </v-row>
    <v-row>
      <v-text-field label="Nama" v-model="ruangan.nama" variant="outlined"></v-text-field>
    </v-row>
    <v-row>
      <v-btn color="blue" @click="submitRuangan">SUBMIT</v-btn>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import { Ruangan } from '@/model/Ruangan'
export default {
  data() {
    return {
      ruangan: {
        kode: '',
        nama: ''
      }
    }
  },
  methods: {
    submitRuangan() {
      if (!this.ruangan.kode && !this.ruangan.nama) {
        alert('Field Kode Ruangan dan Nama belum terisi')
      } else if (!this.ruangan.kode) {
        alert('Field Kode Ruangan belum terisi')
      } else if (!this.ruangan.nama) {
        alert('Field Nama belum terisi')
      } else {
        alert('Data Ruangan ' + this.ruangan.nama + ' berhasil disimpan')
        this.ruangan = {
          kode: '',
          nama: ''
        }
      }
    }
  }
}
</script>
