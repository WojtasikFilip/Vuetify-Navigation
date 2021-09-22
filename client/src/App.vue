<template>
  <v-app>
    <v-app-bar class="blue" app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" class="white--text"></v-app-bar-nav-icon>
      <span class="white--text title">Layout Demo</span>
    </v-app-bar>
    <v-navigation-drawer app hide-overlay disable-resize-watcher v-model="drawer">
      <v-row>
        <v-col cols="6">
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title class="text-h6"> Menu </v-list-item-title>
              <v-list-item-subtitle style="grey"> Please select</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-col>

        <v-col cols="6">
          <v-btn text @click="drawer = false" class="mt-4" float="right">Close</v-btn>
        </v-col>
      </v-row>
      <v-divider> </v-divider>

      <v-list-item-group active-class="blue white--text">
        <v-list-item link v-for="(route, i) in routes" :key="i" :to="route.link">
          {{ route.name }}
        </v-list-item>
      </v-list-item-group>
    </v-navigation-drawer>
    <v-main class="yellow"> </v-main>
  </v-app>
</template>
<!-- @Professor alles ist verbunden, aber der Text aus den Views wird aus irgendeinem Grund nicht angezeigt-->
<script>
export default {
  name: 'App',

  data: () => ({
    //
    routes: [
      { link: '/', name: 'Home' },
      { link: '/products', name: 'Products' },
      { link: '/team', name: 'Team' },
      { link: '/about', name: 'About' },
    ],
    drawer: false,
  }),
};
</script>
