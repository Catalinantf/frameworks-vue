<template>
  <v-carousel v-model="model">
    <v-carousel-item
        v-for="(character, index) in characters"
        :key="index"
    >
    <images :character="character" />
      <v-sheet
        :index="index"
        height="100%"
        tile
      >
        <v-row
          class="fill-height"
          align="center"
          justify="center"
        >
          <div class="text-h2">
            Slide {{ i + 1 }}
          </div>
        </v-row>
      </v-sheet>
    </v-carousel-item>
  </v-carousel>
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
