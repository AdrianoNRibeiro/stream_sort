<script setup>

</script>

<template>
    <nav class="navbar navbar-expand-lg navbar-dark color-themebar">
  <div class="container-fluid">
    <router-link to="/" class="navbar-brand">
      <img src='../../public/img/streaming2.png' alt="Logo" width="50" height="50" class="d-inline-block align-text-top">
    </router-link>
    <div class="title-name">
      <p class="title-nameFirst">Streaming <span class="title-nameSecond" style="font-size: 0.8em;">Sort</span></p>
    </div>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse menu-streaming" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item">
          <router-link class="nav-link" aria-current="page" to="/">Home</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/about">About</router-link>
        </li>
      </ul>
    </div>
  </div>
</nav>
</template>

<style>
:root {
  --color1 : #f23e02 ;
  --color2 : #fef5c8 ;
  --color3 : #00988d ;
  --color4 : #2c6b74 ;
  --color5 : #013750 ;

  --font-title: Vampiro One;
  --font-title2: Bio Rhyme;
}


.color-themebar {
  background-color: var(--color5);
}

.title-name {
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: start;
  width: 300px;
  height: 40px;
  text-align: center;
  margin: 10px 5px 0px 5px;
  
}

.title-nameFirst {
  color: var(--color1);
  font-family: "Vampiro One", system-ui;
  font-weight: 400;
  font-style: normal;
  font-size: 1.5em;
}

.title-nameSecond {
 color: var(--color3);
 font-family: "BioRhyme Expanded", serif;
}

.menu-streaming {
  justify-content: end;
}

.nav-item {
  font-family: "Josefin Sans", sans-serif !important;
  font-size: 1.3em !important;
}
</style>