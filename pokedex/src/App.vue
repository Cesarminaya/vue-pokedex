<template>
  <div id="app">
    <router-view>
      <Navbar />
      <PokemonList />
    </router-view>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Navbar from "@/components/Navbar.vue"; // @ is an alias to /src
import PokemonList from "@/components/PokemonList.vue";

@Component({
  components: {
    Navbar,
    PokemonList,
  },
})
export default class Home extends Vue {}
</script>

<style>
* {
  padding: 0px;
  margin: 0px;
}

</style>
