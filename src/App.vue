<template>
  <v-app id="inspire">
    <v-card-title>
      <v-toolbar flat dark class="elevation-2" color="cyan">
        <v-toolbar-title>vuetify-select-code  {{value}}</v-toolbar-title>
      </v-toolbar>
    </v-card-title>
    <v-card-text>
      <v-container>
        <v-row>
          <v-col cols="4" sm="4" md="4">
            <VuetifySelectCode v-model="value" v-bind:label1="label1" v-bind:label2="label2" v-bind:items="items" v-bind:options="options"/>
          </v-col>
          <br />
          <br />
        </v-row>
      </v-container>
    </v-card-text>
  </v-app>
</template>

<script>
import VuetifySelectCode from "./components/VuetifySelectCode.vue";

export default {
  name: "app",
  components: {
    VuetifySelectCode
  },
  data: () => ({
    value: "2",
    label1: "Code",
    label2: "Description",
    items: [
      { text: "1 - Dessert", value: "1" },
      { text: "2 - Calories", value: "2" },
      { text: "3 - Fat", value: "3" },
      { text: "4 - Protein", value: "4" },
      { text: "140 - Iron", value: "140" }
    ],
    options: {
      outlined: true,
      clearable: true
    },
  })
};
</script>
