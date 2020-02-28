<template>
  <v-app>
    <v-app-bar dark app>
      <v-app-bar-nav-icon @click="goBack">
        <v-icon>mdi-reply</v-icon>
      </v-app-bar-nav-icon>
    </v-app-bar>
    <v-content class="flex-column">
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  data: () => ({
    //
  }),
  methods: {
    goBack: function() {
      if (this.$router.currentRoute.path !== '/') {
        this.$router.go(-1);
      }
    }
  },
};
</script>

<style lang="scss">
  * {
    box-sizing: border-box;
  }
</style>
