<template>
  <v-simple-table fixed-header height="300px">
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">ROW</th>
          <th class="text-left">Name</th>
          <th class="text-left">Delete</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index) in desserts" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ item.name }}</td>
          <td>
            <v-btn
              color="red darken-3 white--text"
              depressed
              @click="deleteTodo(index)"
            >
              <v-icon left>
                {{ icons.mdiDelete }}
              </v-icon>
              Delete
            </v-btn>
          </td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
</template>

<script>
import { mdiAccount, mdiPencil, mdiShareVariant, mdiDelete } from "@mdi/js";
export default {
  data() {
    return {
      icons: {
        mdiAccount,
        mdiPencil,
        mdiShareVariant,
        mdiDelete,
      },
    };
  },
  props: ["desserts"],
  methods: {
    deleteTodo(index) {
      this.desserts.splice(index, 1);
    },
  },
};
</script>

<style></style>
