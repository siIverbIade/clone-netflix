<template>
  <v-app>
    <v-navigation-drawer class="d-md-none" v-model="drawer" absolute temporary>
      <v-list nav dense>
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <div v-for="item in menu_itens" :key="item.name">
            <v-list-item :to="item.path">
              <v-list-item-title>{{ item.name }}</v-list-item-title>
            </v-list-item>
          </div>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar color="black" app dense>
      <v-app-bar-nav-icon @click="drawer = !drawer" class="d-sm-none">
      </v-app-bar-nav-icon>
      <v-avatar size="125">
        <v-img contain :src="require('@/assets/img/netflix-logo.png')" />
      </v-avatar>
      <v-spacer></v-spacer>
      <div
        class="d-none d-sm-block"
        v-for="item in menu_itens"
        :key="item.name"
      >
        <v-btn plain :to="item.path">{{ item.name }}</v-btn>
      </div>
    </v-app-bar>

    <v-main>
      <!-- Provides the application the proper gutter -->
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer app> </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      group: false,
      menu_itens: [
        { name: "Filmes", path: "/filmes" },
        { name: "Séries", path: "/series" },
        { name: "Documentários", path: "/documentarios" },
        { name: "Animação", path: "/animacao" },
      ],
    };
  },
};
</script>
