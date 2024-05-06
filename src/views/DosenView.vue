<template>
  <v-container>
    <v-row>
      <h1>Entry Data Dosen</h1>
    </v-row>
    <v-row>
      <v-text-field label="NIDN" variant="outlined" v-model="dosen.nidn"></v-text-field>
    </v-row>
    <v-row>
      <v-text-field label="Nama" v-model="dosen.nama" variant="outlined"></v-text-field>
    </v-row>
    <v-row>
      <v-btn color="blue" @click="submitDosen">SUBMIT</v-btn>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import { Dosen } from '@/model/Dosen'
export default {
  data() {
    return {
      dosen: {
        nidn: '',
        nama: ''
      }
    }
  },
  methods: {
    submitDosen() {
      if (!this.dosen.nidn && !this.dosen.nama) {
        alert('Field NIDN dan Nama belum terisi')
      } else if (!this.dosen.nidn) {
        alert('Field NIDN belum terisi')
      } else if (!this.dosen.nama) {
        alert('Field Nama belum terisi')
      } else {
        alert('Data Dosen ' + this.dosen.nama + ' berhasil disimpan')
        this.dosen = {
          nidn: '',
          nama: ''
        }
      }
    }
  }
}
</script>
