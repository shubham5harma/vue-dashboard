<template>
  <nav>
    <v-app-bar color="white" dark app>
      <v-app-bar-nav-icon
        class="black--text"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>
      <v-toolbar-title class="text-uppercase ">
        <!-- <span class="font-weight-light black--text">Attabot</span> -->
        <!-- <span class="black--text">Home</span> -->
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-menu offset-y>
        <!-- <template v-slot:activator="{ on }">
          <v-btn text v-on="on">
            <v-icon class="black--text" left>expand_more</v-icon>
            <span class="black--text">Menu</span>
          </v-btn>
        </template> -->
        <v-list flat>
          <v-list-item
            v-for="link in links"
            :key="link.text"
            router
            :to="link.route"
            active-class="border"
          >
            <v-list-item-title>{{ link.text }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
      <!-- <v-btn text> -->
      <!-- <span class="black--text text-capitalize">Logout</span> -->
      <!-- <v-icon class="black--text" right>exit_to_app</v-icon> -->
      <!-- </v-btn> -->
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" dark app class="sidebar darken-4">
      <v-layout column align-center>
        <v-flex class="mt-5">
          <img class="sidebar_logo" src="../assets/rpsg.png" alt="" />
        </v-flex>
        <v-flex class="mt-4 mb-4">
          <Popup />
        </v-flex>
      </v-layout>
      <v-list flat>
        <v-list-item
          v-for="link in links"
          :key="link.text"
          router
          :to="link.route"
          active-class="border"
          class="border1"
        >
          <v-list-item-action>
            <v-icon>{{ link.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{ link.text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>
<script>
export default {
  data: () => ({
    drawer: true,
    links: [
      { icon: "folder_open", text: "DISHA", route: "/home/disha" },
      { icon: "dashboard", text: "IVR", route: "/home/ivr" },
    ],
  }),
};
</script>
<style scoped>
.border {
  background-color: #f28a3e;
}

.sidebar_logo {
  height: 50px;
  width: 146px;
  padding: 6px;
  margin-right: 30px;
}
</style>
