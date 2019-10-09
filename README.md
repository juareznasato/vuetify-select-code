# vuetify-select-code

If you use Vuejs with Vuetify and need a v-select to select by entering a code. Maybe it can help you.

## Dependency
- VueJS
- Vuetify
- mdi

## Links
<p><a href="https://f8w0c.csb.app/">See DEMO here</a></p>
<p><a href="https://github.com/juareznasato/vuetify-select-code" target="_blank">GitHub</a></p>
<p><a href="https://www.npmjs.com/package/vuetify-select-code" target="_blank">npm</a></p>

## Install:
```
$ npm install vuetify-select-code --save

Register component:

1- Create a src/plugins/vuetify-select-code.js file with:
import Vue from "vue";
import VuetifySelectCode from "vuetify-select-code";
Vue.use(VuetifySelectCode);
export default VuetifySelectCode;

2- Add to src/mains.js file:
import "./plugins/vuetify-select-code.js";

Parent component:
<template>
  <div>
    <vuetify-select-code v-model="value" v-bind:label1="label1" v-bind:label2="label2" v-bind:items="items" v-bind:options="options"/>
     Parent v-model: {{ value }}
  </div>
</template>

<script>
export default {
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

