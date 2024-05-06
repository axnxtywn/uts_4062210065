<template>
  <v-container>
    <v-row>
      <h2>Entry Data Mahasiswa</h2>
    </v-row>
    <v-row>
      <v-text-field label="NPM" variant="outlined" v-model="mhs.npm"></v-text-field>
    </v-row>
    <v-row>
      <v-text-field label="Nama" v-model="mhs.nama" variant="outlined"></v-text-field>
    </v-row>
    <v-row>
      <v-text-field label="IPK" v-model="mhs.ipk" variant="outlined"></v-text-field>
    </v-row>
    <v-row>
      <v-btn color="blue" @click="submitMahasiswa">SUBMIT</v-btn>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import { Mahasiswa } from '@/model/Mahasiswa'
export default {
  data() {
    return {
      mhs: new Mahasiswa('', '', 0),
      dataMahasiswa: []
    }
  },
  methods: {
    submitMahasiswa() {
      if (!this.mhs.npm && !this.mhs.nama && !this.mhs.ipk) {
        alert('Field NPM, Nama, dan IPK belum terisi')
      } else if (!this.mhs.nama && !this.mhs.ipk) {
        alert('Field Nama dan IPK belum terisi')
      } else if (!this.mhs.npm && !this.mhs.ipk) {
        alert('Field NPM dan IPK belum terisi')
      } else if (!this.mhs.npm && !this.mhs.nama) {
        alert('Field NPM dan Nama belum terisi')
      } else if (!this.mhs.npm) {
        alert('Field NPM belum terisi')
      } else if (!this.mhs.nama) {
        alert('Field Nama belum terisi')
      } else if (!this.mhs.ipk) {
        alert('Field IPK belum terisi')
      } else if (this.mhs.ipk >= 0 && this.mhs.ipk <= 5) {
        if (this.dataMahasiswa.length < 5) {
          alert('Data Mahasiswa ' + this.mhs.nama + ' berhasil disimpan')
          this.dataMahasiswa.push({ npm: this.mhs.npm, nama: this.mhs.nama, ipk: this.mhs.ipk })
          this.mhs = new Mahasiswa('', '', 0)
        } else {
          alert('Jumlah maksimal Data Mahasiswa telah tercapai (5)')
          this.mhs = new Mahasiswa('', '', 0)
        }
      } else {
        alert('IPK harus diantara 0 sampai 4')
      }
    }
  }
}
</script>
