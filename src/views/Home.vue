<template>
  <v-container class="home">
    <v-row class="home__header flex-column">
      <v-col>
        <h1>Split Bill</h1>
      </v-col>
      <v-col>
        <v-text-field
          solo-inverted
          label="Menu"
          prepend-inner-icon
          hide-details
          v-model="order.menu"
        ></v-text-field>
      </v-col>
      <v-col>
        <v-text-field
          solo-inverted
          label="Price"
          prepend-inner-icon
          hide-details
          v-model="order.price"
        ></v-text-field>
      </v-col>
      <v-col align-self="center">
        <v-btn text icon color="pink" @click="addItem" :disabled="disableRule">
          <v-icon color="#000000" large>mdi-check-circle</v-icon>
        </v-btn>
      </v-col>
    </v-row>
    <v-row class="home__body flex-column">
      <v-col>
        <h2>Here's the menu that you ordered</h2>
        <v-data-iterator
          :items="menu"
          :disable-pagination="true"
          :disable-filtering="true"
          :disable-sort="true"
          dark
          hide-default-footer
        >
          <template>
            <v-row>
              <v-col cols="12">
                <v-card>
                  <v-list dense>
                    <v-list-item v-for="(item, index) in menu" :key="index">
                      <v-list-item-content>{{ item.menu }} :</v-list-item-content>
                      <v-list-item-content class="align-end">{{ item.price }}</v-list-item-content>
                    </v-list-item>
                  </v-list>
                </v-card>
              </v-col>
            </v-row>
          </template>
        </v-data-iterator>
      </v-col>
    </v-row>
    <v-row class="home__footer">
      <v-col>
        <v-btn block dark>Next</v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>

export default {
  name: 'Home',
  components: {},
   data: () => ({
    menu: [],
    order: {
      menu: "",
      price: ""
    },
    lorem: "Lorem."
  }),
  computed: {
    disableRule: function() {
      return !this.order.menu || !this.order.price;
    }
  },
  methods: {
    addItem: function() {
      this.menu.push(this.order);
    }
  },
}
</script>

<style lang="scss">
  .home {
    height: 100vh;
    &__header {
      text-align: center;
    }
    &__body {
    }
    &__footer {
    }
  }
</style>
