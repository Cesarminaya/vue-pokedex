<template>
  <div class="container">
    <div class="container-fluid black">
      <div class="container center">
        <p>
          La serie de videojuegos de Pokémon, referida por los fanes como la
          "saga principal", son videojuegos de rol desarrollados por Game Freak
          y publicados para videoconsolas portátiles de Nintendo.
        </p>
      </div>
    </div>
    <div class="container-fluid">
      <div class="parallax"></div>
    </div>
    <div class="container-fluid black">
      <div class="container center">
        <p>
          La serie se divide en generaciones Pokémon, las cuales son los grupos
          de videojuegos que aparecen en un cierto período y que comparten una
          serie de características similares, concretamente los personajes y
          criaturas (Pokémon) y la región donde se sucede la historia. Estas
          generaciones suelen corresponderse con las generaciones de las
          consolas. La aparición sucesiva de generaciones suele tener como
          consecuencia la publicación de nuevas entregas de diversos productos
          derivados de los videojuegos, como la serie de anime Pokémon.
        </p>
      </div>
    </div>
    <div class="container-fluid">
      <div class="parallax"></div>
    </div>
  </div>
</template>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

p {
  color: #fff;
}

.container-fluid {
  width: 100%;
}

.container {
  max-width: 1290px;
  width: 100%;
  margin: auto;
  padding: 32px;
}

.center {
  text-align: center;
}
.black {
  background-color: #252525;
}

.parallax {
  height: 500px;
  background-image: url("../assets/parallax.jpg");
  background-size: cover;
  background-attachment: fixed;
}
</style>