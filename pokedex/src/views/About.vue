<template>
  <div class="about">
    <Navbar />
    <Parallax/>
    <router-view />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Navbar from "@/components/Navbar.vue"; // @ is an alias to /src
import Parallax from '@/components/parallax.vue';
@Component({
  components: {
    Navbar,
    Parallax
  },
})
export default class Home extends Vue {}
</script>

