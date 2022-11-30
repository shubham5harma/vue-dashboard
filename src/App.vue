<template>
  <v-app>
    <Navbar />
    <v-content class="ma-4">
      <transition name="slide">
        <router-view></router-view>
      </transition>
    </v-content>
    <Footer />
  </v-app>
</template>

<script>
import Navbar from "@/components/Navbar";
import Footer from "@/components/Footer";
export default {
  name: "App",

  components: {
    Navbar,
    Footer,
  },

  data: () => ({}),
};
</script>
