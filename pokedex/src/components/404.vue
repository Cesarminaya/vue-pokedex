<template>
  <div class="pagenotfound">
    <div id="main">
      <div class="fof">
        <h1>Esta página no está disponible</h1>
        <h2>
          Es posible que el enlace esté roto o que se haya eliminado la página.
          Verifica que el enlace que quieres abrir es correcto.
        </h2>
      </div>
      <div class="button button-2"><a href="/">Ir a la Pokédex</a></div>
    </div>
  </div>
</template>

<style scoped>
* {
  transition: all 0.6s;
}

html {
  height: 100%;
}
h2 {
  color: #74756b;
  position: fixed;
  top: 50%;
  left: 50%;
  /* bring your own prefixes */
  transform: translate(-50%, -50%);
}
body {
  font-family: "Lato", sans-serif;
  color: #888;
  margin: 0;
}

#main {
  display: table;
  width: 100%;
  height: 100vh;
  text-align: center;
}

.fof {
  display: table-cell;
  vertical-align: middle;
  position: relative;
  bottom: 62px;
}

.fof h1 {
  font-size: 50px;
  display: inline-block;
  padding-left: 240px;
  animation: type 0.5s alternate infinite;
}
@keyframes type {
  from {
    box-shadow: inset -3px 0px 0px #888;
  }
  to {
    box-shadow: inset -3px 0px 0px transparent;
  }
}
.button {
  width: 170px;
  margin-top: 500px;
  padding-bottom: 30px;
  font-size: 18px;
  text-align: center;
  text-transform: uppercase;
  font-weight: 600;
  margin-right: 30px;
  margin-bottom: 30px;
  cursor: pointer;
  display: inline-block;
  position: relative;
  right: 500px;
  bottom: 120px;
}
button > a:hover {
  color: #d35670;
}

.button-2:hover {
  background-position: 100%;
  color: #d35670;
}
a {
  text-decoration: none;
  color: #d35670;
}
.button-2 > a:hover {
  color: rgb(209, 197, 181);
}
</style>