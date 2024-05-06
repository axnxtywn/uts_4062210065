<template>
  <v-navigation-drawer v-model="drawer" :rail="rail" permanent @click="rail = false">
    <v-list>
      <v-list-item
        prepend-avatar="https://randomuser.me/api/portraits/men/85.jpg"
        title="Ahmad Agung Setyawan"
      >
      </v-list-item>
    </v-list>

    <v-divider></v-divider>

    <v-list density="compact" nav>
      <v-list-item title="Home" value="home" :to="'/'">
        <template v-slot:prepend>
          <img src="/src/assets/folder-fill.svg" style="margin-right: 10px" />
        </template>
      </v-list-item>
      <v-list-item title="Dosen" value="Dosen" :to="'/Dosen'">
        <template v-slot:prepend>
          <img src="/src/assets/people-fill.svg" style="margin-right: 10px" />
        </template>
      </v-list-item>
      <v-list-item title="Mahasiswa" value="mahasiswa" :to="'/mahasiswa'">
        <template v-slot:prepend>
          <img src="/src/assets/star-fill.svg" style="margin-right: 10px" />
        </template>
      </v-list-item>
      <v-list-item title="Ruangan" value="ruangan" :to="'/ruangan'">
        <template v-slot:prepend>
          <img src="/src/assets/star-fill.svg" style="margin-right: 10px" />
        </template>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
  <v-main style="height: 250px"></v-main>
</template>

<script>
export default {
  data() {
    return {
      drawer: true,
      rail: true
    }
  }
}
</script>
