<template>
  <v-app class="app">
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
};
</script>

<style lang="scss">
  * {
    box-sizing: border-box;
  }
</style>
