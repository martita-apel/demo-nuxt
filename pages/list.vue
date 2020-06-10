<template>
  <v-container fluid>
    <v-layout class="mx-3">
      <v-row col="4">
        <v-card v-for="(p, i) in personajes" :key="i" class="ma-2">
          <v-img :src="p.imagen"></v-img>
          <v-card-title>{{ p.nombre }}</v-card-title>
          <v-card-subtitle> {{ p.subtitulo }}</v-card-subtitle>
          <v-card-actions>
            <v-btn text>Share</v-btn>
            <v-btn color="orange" text>Explore</v-btn>
            <v-spacer></v-spacer>
            <v-btn icon @click="show = !show">
              <v-icon>{{
                show ? "mdi-chevron-up" : "mdi-chevron-down"
              }}</v-icon></v-btn
            >
          </v-card-actions>

          <v-expand-transition>
            <div v-show="show">
              <v-divider></v-divider>
              <v-card-text>
                {{ p.texto }}
              </v-card-text>
            </div>
          </v-expand-transition>
        </v-card>
      </v-row>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      personajes: [
        {
          id: 1,
          nombre: "Morty",
          subtitulo: "Nieto de Rick, lo sigue en sus aventuras",
          imagen: "https://rickandmortyapi.com/api/character/avatar/2.jpeg",
          texto:
            "Posee una inteligencia pobre, es de estatura baja para su edad y está enamorado de una compañera de escuela llamada Jessica."
        },
        {
          id: 2,
          nombre: "Rick",
          subtitulo: "Genio, irresponsable y con poca cordura",
          imagen: "https://rickandmortyapi.com/api/character/avatar/1.jpeg",
          texto:
            "Rick Sánchez es un ejemplo del típico científico loco. Por diferentes razones termina mudándose a la casa de su hija Beth y en ese momento se encuentra con su nieto Morty; un joven de 14 años tímido y no muy listo. Al juntarse con su nieto, Rick y Morty viven una variedad de aventuras a lo largo del Cosmos y Universos paralelos."
        },
        {
          id: 3,
          nombre: "Summer",
          subtitulo: "Hermana mayor de Morty",
          imagen: "https://rickandmortyapi.com/api/character/avatar/3.jpeg",
          texto:
            "Típica adolescente que suele ser superficial y obsesionada con mejorar su imagen frente a sus amigos. "
        },
        {
          id: 4,
          nombre: "Beth",
          subtitulo: "Madre de Morty y Summer",
          imagen: "https://rickandmortyapi.com/api/character/avatar/4.jpeg",
          texto:
            "Al igual que su padre, bebe mucho, pero a diferencia de él, es muy seria ante las situaciones y a la vez es muy despreocupada en ocasiones."
        },
        {
          id: 5,
          nombre: "Jerry",
          subtitulo: "Padre de Morty y de Summer",
          imagen: "https://rickandmortyapi.com/api/character/avatar/5.jpeg",
          texto:
            "Es una persona bastante patética; es un mal padre de familia, es inseguro de sí mismo y tiene problemas en su matrimonio con Beth."
        }
      ],
      show: false
    };
  }
};
</script>
<style>
template {
  background-color: white !important;
}
.v-card {
  background-color: white;
}
</style>
