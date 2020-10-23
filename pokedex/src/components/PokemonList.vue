<template>
  <div class="pokemonlist">
    <div class="card" v-for="pokemon in pokedex" :key="pokemon.id">
      <h2>{{ pokemon.id }}</h2>
      <img :src="pokemon.sprite" class="cover" />
      <div class="container">
        <h4>
          <b>{{ pokemon.name }}</b>
        </h4>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Axios from "axios";

@Component
export default class PokemonList extends Vue {
  /* eslint-disable */
  pokedex: any = [];

  async getAll() {
    const { data } = await Axios.get(
      "https://pokeapi.co/api/v2/pokemon/?limit=150"
    );
    this.pokedex = data.results.map((item: any) => {
      const id = item.url.split("/")[6];
      return {
        id,
        name: item.name,
        sprite: `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${id}.png`,
      };
    });
  }
 async mounted() {
    this.getAll();
  }
}
</script>

<style scoped>
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  width: 20%;
  padding: 30px;
  margin-top: 20px;
  margin-left: 50px;
  text-align: center;
}
div.pokemonlist{
  display: flex;
  flex-flow: row; 
  flex-direction: row;
  flex-wrap: wrap;
  position: relative;
  bottom: 85px;
}
div.pokemonlist{
  float: left;
}
img.cover {
  width: 120px;
  height: 120px;
  margin-block: 10px;
}
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

.container {
  padding: 2px 16px;
}
h4 > b {
  font-size: 16pt;
}
</style>