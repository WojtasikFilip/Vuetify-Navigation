<template>
  <v-app>
    <v-app-bar class="grey lighten-5" height="74" app>
      <img class="mx-2" src="@/images/BMW.svg.png" style="height:150px; margin-top:100px" />
      <span class="text-truncate text-h4 blue-grey--text darken-1" style="font-family: Poppins"
        >A Car With a Mission</span
      >
      <v-spacer></v-spacer>
      <div class="hidden-md-and-down">
        <v-btn active-class="white--text red" class="white--text black" to="/" exact>Home</v-btn>
        <v-btn active-class="white--text red" class="white--text black ml-5" to="/products" exact
          >Products</v-btn
        >
        <v-btn active-class="white--text red" class="white--text black ml-5" to="/about" exact>About</v-btn>
      </div>

      <v-app-bar-nav-icon
        v-if="!drawer"
        @click.stop="drawer = !drawer"
        class="black--text hidden-lg-and-up"
      ></v-app-bar-nav-icon>
    </v-app-bar>

    <v-navigation-drawer app hide-overlay disable-resize-watcher v-model="drawer" right>
      <v-row>
        <v-col cols="6">
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title class="text-h6">
                Menu
              </v-list-item-title>
              <v-list-item-subtitle>
                Please select
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-col>
        <v-col cols="6">
          <v-btn text @click="drawer = false" class="mt-4" float="right">Close</v-btn>
        </v-col>
      </v-row>

      <v-divider></v-divider>
      <v-list-item-group active-class="red white--text">
        <v-list-item link v-for="(route, i) in routes" :key="i" :to="route.link">
          {{ route.name }}
        </v-list-item>
      </v-list-item-group>
    </v-navigation-drawer>
    <v-main>
      <div class="d-flex">
        <div style="width:200px"></div>
        <div class="mt-10" style="flex:1"><router-view></router-view></div>
      </div>
    </v-main>
  </v-app>
</template>
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
