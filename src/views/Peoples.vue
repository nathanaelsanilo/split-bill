<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Peoples</h1>
      </v-col>
    </v-row>
    <v-row class="flex-column">
      <v-col>
        <h3>Type your friends name below</h3>
      </v-col>
      <v-col>
        <v-text-field
          solo-inverted
          label="Menu"
          prepend-inner-icon
          hide-details
          v-model="peopleName"
        ></v-text-field>
      </v-col>
      <v-col>
        <v-btn block dark @click="addPeople">Add</v-btn>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <v-list-item v-for="(item, index) in peopleList" :key="index">
          <v-list-item-content>
            <v-list-item-title>{{ index + 1 }}. {{ item }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  name: 'Peoples',
  data: () => ({
    peopleList: [],
    peopleName: ''
  }),
  methods: {
    addPeople: function() {
      this.peopleList.push(this.peopleName);
    }
  },
}
</script>
