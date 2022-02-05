<template>
  <v-form v-model="valid">
    <v-row>
      <v-col cols="12" md="4">
        <v-select
          v-model="select"
          :items="items"
          :rules="[(v) => !!v || 'Item is required']"
          label="Item"
          required
          dense
          outlined
        ></v-select>
      </v-col>

      <v-col cols="12" md="4">
        <v-text-field
          v-model="name"
          :rules="nameRules"
          label="Name"
          required
          dense
          outlined
        ></v-text-field>
      </v-col>

      <v-col cols="12" md="4">
        <v-btn
          :disabled="!valid"
          color="success"
          class="mr-4"
          @click="validate"
        >
          Add
        </v-btn>
      </v-col>
    </v-row>
  </v-form>
</template>

<script>
export default {
  data() {
    return {
      valid: true,
      name: "",
      nameRules: [(v) => !!v || "Name is required"],
      emailRules: [
        (v) => !!v || "E-mail is required",
        (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
      ],
      select: null,
      items: ["SA", "Web", "Biology", "Math"],
    };
  },
  methods: {
    validate() {
      this.$emit("Input", this.select, this.name);
      (this.select = ""), (this.name = "");
    },
  },
};
</script>

<style></style>
