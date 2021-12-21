<template>
  <v-container>
    <v-row>
      <v-col
        v-for="(character, index) in characters"
        :key="index"
        cols="12"
        sm="4"
      >
        <Card :character="character" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import Card from "@/components/Card";
import axios from "axios";

export default {
  components: { Card },

  data() {
    return {
      characters: null,
    };
  },
  mounted() {
    const url =
      "https://rickandmortyapi.com/api/character/[1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,20,21]";
    axios.get(url).then((response) => (this.characters = response.data));
  },
};
</script>
