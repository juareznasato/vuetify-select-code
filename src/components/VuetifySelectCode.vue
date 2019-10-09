<template>
  <div>
    <template>
      <v-row dense>
        <v-col cols="2" sm="2" md="2">
          <v-text-field
            v-bind:label="label1"
            v-bind:outlined="options.outlined"
            v-model="modTextField"
          ></v-text-field>
        </v-col>
        <v-col cols="10" sm="10" md="10">
          <v-select
            v-bind:label="label2"
            v-bind:outlined="options.outlined"
            v-bind:clearable="options.clearable"
            v-model="modSelect"
            v-bind:items="items"
            v-bind:menu-props="{openOnClick: true, closeOnClick: true, closeOnContentClick: true, value: selectOpen}"
          ></v-select>
        </v-col>
      </v-row>
    </template>
  </div>
</template>

<script>
export default {
  model: { prop: "value", event: "input" },
  props: {
    value: {
      type: [String],
      default: null
    },
    label1: {
      type: String,
      default: "Code"
    },
    label2: {
      type: String,
      default: "Description"
    },
    items: {
      type: Array,
      default: function() {
        return [];
      }
    },
    options: {
      type: Object,
      default: function() {
        return {
          outlined: true,
          clearable: true
        };
      }
    }
  },
  data: () => ({
    modTextField: "",
    modSelect: "",
    selectOpen: false
  }),
  created() {
    this.modSelect = this.value;
  },
  watch: {
    modTextField() {
      if (this.existValue()) {
        this.modSelect = this.modTextField;
        this.selectOpen = false;
        this.$emit("input", this.modSelect);
      } else {
        this.selectOpen = true;
        this.$emit("input", null);
      }
    },
    modSelect() {
      this.modTextField = this.modSelect;
      this.selectOpen = false;
      this.$emit("input", this.modSelect);
    }
  },
  methods: {
    existValue() {
      let result = false;
      for (var i = 0; i < this.items.length; i++) {
        let value = this.items[i].value;
        if (value === this.modTextField) {
          result = true;
        }
      }
      return result;
    }
  }
};
</script>