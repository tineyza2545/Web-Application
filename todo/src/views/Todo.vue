<template>
  <v-container>
    <Data @Input="validate"></Data>
    <Excel :desserts="desserts"></Excel>
  </v-container>
</template>

<script>
import Data from "../components/Data.vue";
import Excel from "../components/Excel.vue";
export default {
  data: () => ({
    desserts: [],
  }),
  desserts: "Input",
  methods: {
    validate(select, name) {
      this.desserts.push({
        name: select + " : " + name,
      });
    },
  },
  components: { Data, Excel },
};
</script>

<style></style>
