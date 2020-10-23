<template>
  <div class="navbar">
    <img class="once" src="@/assets/pokedex.png" v-on:click="Touch()" />
    <nav>
      <router-link tag="li" :to="{ name: 'Home' }" exact>Pokédex</router-link>
      <router-link tag="li" :to="{ name: 'About' }" exact>Acerca de</router-link>
    </nav>
    <PokemonSearch />
    <router-view />
  </div>
</template>


<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import PokemonSearch from "@/components/PokemonSearch.vue";
@Component({
  components: {
    PokemonSearch,
  },
})
export default class Home extends Vue {
  Touch() {
    this.$router.push("/").catch((error) => {
      if (
        error.name !== "NavigationDuplicated" &&
        !error.message.includes(
          "Avoided redundant navigation to current location"
        )) 
        console.log(error);
    });
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  padding: 0px;
  margin: 0px;
}
li {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 22px;
  list-style: none;
  display: inline-block;
  padding: 9px;
  position: relative;
  left: 85px;
  bottom: 59px;
}
li:hover {
  background-color: aliceblue;
  border-radius: 2px;
  cursor: pointer;
}
img {
  width: 60px;
  height: 60px;
  padding: 5px;
  cursor: pointer;
  margin-left: 10px;
  margin-top: 10px;
}
img.once:hover {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
  overflow: hidden;
}
li.router-link-exact-active {
  color: #d32f2f;
}
</style>