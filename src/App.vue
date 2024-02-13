<template>
  <header>
    <img src="/src/assets/logo.png" alt="logo" class="logo">
    <nav>
      <ul>
        <li>
          <a href="#presentation">PRESENTATION</a>
        </li>
        <li>
          <a href="#project">PROJET</a>
        </li>
        <li>
          <a href="#team">EQUIPE</a>
        </li>
        <li>
          <a href="#news">ACTU</a>
        </li>
      </ul>
    </nav>
  </header>
  <body>
    <video id="wp-custom-header-video" autoplay loop playsinline muted width="2000" height="1200" src="https://lunetteriedevilleroy.fr/wp-content/uploads/2023/01/demo2e_1.mp4"></video>
    <section id="presentation">
      <h1>Présentation</h1>
    </section>
    <section id="project">
      <h1>Projet</h1>
    </section>
    <section id="team">
      <h1>Equipe</h1>
    </section>
    <section id="news">
      <h1>Actualité</h1>
    </section>
  </body>
</template>

<style lang="scss" scoped>
header {
  height: 100px;
  width: 100%;
  background-color: black;
  display: flex;
  align-items: center;

  .logo {
    width: 100px;
    margin-left: 30px;
  }

  nav {
    width: 100%;

    ul {
      display: flex;
      flex-direction: row;
      justify-content: space-evenly;
      align-items: center;
      list-style: none;

      a {
        color: white;
        text-decoration: none;
        font-size: 23px;
      }
    }
  }
}

body {
  h1 {
    text-align: center;
    font-size: 25px;
  }

  video {
    height: 100%;
    left: 0;
    object-fit: cover;
    top: 0;
    transform: none;
    width: 100%;
  }
}
</style>
