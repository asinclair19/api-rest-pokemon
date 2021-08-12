<template>
  <div class="home">
    <b-container>
      <b-row>
        <pokemon-item v-for="item in datos" :key="item.name" :datos="item"></pokemon-item>
      </b-row>
    </b-container>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from "axios";

const URL_API = "https://pokeapi.co/api/v2/pokemon/";

import pokemonItem from "@/components/PokemonItem.vue";

export default {
  name: "Home",
  components: {
    "pokemon-item": pokemonItem,
  },
  data() {
    return { datos: [] };
  },
  methods: {
    async getPokemon() {
      await axios.get(URL_API).then((response) => {
        this.datos = response.data.results;
        //console.log(response.data.results);
      });
    },
  },
  created() {
    this.getPokemon();
  },
};
</script>
