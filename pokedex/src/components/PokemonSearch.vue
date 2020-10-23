<template>
  <div class="search">
    <nav id="one">
      <div class="cont">
        <label>Buscar</label>
        <input
          type="search"
          placeholder="Buscar Pokémon"
          title="Presione Esc para supender la búsqueda"
          v-model="Search"
          />
      </div>
    </nav>
  </div>
</template>


<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Axios from "axios";

@Component
export default class PokemonSearch extends Vue {
  Search = "";
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

  SearchPokemons() {
    return this.pokedex.filter((pokedexes: any) => {
      return pokedexes.name.toLowerCase().match(this.Search);
    });
  }

  async mounted() {
    this.getAll();
    this.SearchPokemons();
  }
}
</script>

<style>
nav > #one {
  width: 100%;
  height: 60px;
  font-family: sans-serif;
  background: #f1f1f1;
  border-bottom: 4px solid rgba(0, 0, 0, 0.1);
}

.cont {
  height: 100%;
  padding-top: 0px;
  float: right;
}
.cont label {
  color: #8a8a8a;
  font-size: 18px;
  cursor: pointer;
}
input[type="search"] {
  width: 180px;
  margin: 10px;
  padding: 10px 16px;
  border-radius: 32px;
  outline: none;
  border: 2px solid #ccd1d1;
  background: aliceblue;
  transition: all 0.4s;
}
input[type="search"]:focus {
  background: #fff;
  width: 280px;
}
div.search {
  position: relative;
  bottom: 108px;
  right: 20px;
}
</style>