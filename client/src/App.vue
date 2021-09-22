<template>
  <v-app>
    <v-navigation-drawer class="green" app>
      <span class="white--text title">v-navigation-drawer</span>
    </v-navigation-drawer>
    <v-system-bar class="pink" app>
      <span class="white--text title">v-system-bar</span>
    </v-system-bar>
    <v-app-bar class="yellow" app>
      <span class="title">v-app-bar</span>
    </v-app-bar>
    <v-main class="blue">
      <span class="white--text title">v-main</span>
    </v-main>
    <v-footer class="purple" app>
      <span class="white--text title mx-auto">v-footer</span>
    </v-footer>
    <v-bottom-navigation class="cyan" app>
      <span class="white--text title">v-bottom-navigation</span>
    </v-bottom-navigation>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  data: () => ({
    //
  }),
};
</script>
