<template>
  <div>
    <v-img
      gradient="to top right, rgba(0,0,0,.50), rgba(0,0,0,.50)"
      height="500"
      :src="require('@/assets/img/principal.jpg')"
    >
      <v-container class="pa-16" style="position: absolute; bottom: 50px">
        <v-row>
          <v-col>
            <h1>{{ series[0].titulo }}</h1>
            <p class="descricao d-none d-sm-block">{{ series[0].descricao }}</p>
            <p class="d-sm-none">{{ series[0].descricao }}</p>
            <v-btn class="mb-2" height="40" width="200">
              <v-icon left> mdi-play</v-icon>
              Assistir Agora
            </v-btn>
            <v-btn class="mb-2" height="40" width="200">
              <v-icon left> mdi-information </v-icon>Mais Informações
            </v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-img>
    <v-sheet class="mx-auto" elevation="8">
      <v-slide-group active-class="success" show-arrows>
        <v-slide-item v-for="n in 13" :key="n" v-slot="{ active, toggle }">
          <v-hover v-slot="{ hover }">
            <v-card
              :color="active ? undefined : 'grey lighten-1'"
              height="320"
              width="240"
              class="ma-1"
              @click="toggle"
            >
              <v-img
                :height="320 + hover * 20"
                :width="240 + hover * 80"
                :src="require('@/assets/img/' + n + '.jpg')"
              ></v-img>
            </v-card>
          </v-hover>
        </v-slide-item>
      </v-slide-group>
    </v-sheet>
  </div>
</template>

<script>
export default {
  data() {
    return {
      series: [
        {
          titulo: "O GAMBITO DA RAINHA",
          descricao:
            "Conta a história de Beth Harnmon, uma menina orfã que se revela um prodígio do xadrez. mas agora, aos 22 anos, ela precisa enfrentar seu vício para conseguir se tornar a maior jogadora do mundo.",
        },
      ],
    };
  },
};
</script>

<style>
.descricao {
  width: 75%;
}
</style>